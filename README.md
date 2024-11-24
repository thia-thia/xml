In BaseX

1.
for $x in /bookstore/book
where $x/price>30
return $x/title

2.
for $x in /bookstore/book
where $x/price>30
order by $x/title
return $x/title

3.
<ul>
{
for $x in /bookstore/book/title
order by $x
return <li>{$x}</li>
}
</ul>

4.
<ul>
{
for $x in /bookstore/book/title
order by $x
return <li>{data($x)}</li>
}
</ul>

5.
for $x in /bookstore/book
return if ($x/@category="children")
then <child>{data($x/title)}</child>
else <adult>{data($x/title)}</adult>

6.
<html>
<body>

<h1>Bookstore</h1>

<ul>
{
for $x in /bookstore/book
order by $x/title
return <li>{data($x/title)}. Category: {data($x/@category)}</li>
}
</ul>

</body>
</html>
