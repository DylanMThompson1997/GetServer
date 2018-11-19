# GetServer
This is a server that queries the Northwind database using HTTP GET requests in a LINQ syntax, and publishes the results to a web page

To view the code that comprises the server, view the lone C# file. To actually run the service, download the zip file and run the compile script, then open the service and test it in a browser, using the URLs, which should work when copied into a browser (the ones with spaces will not work directly from here).

--- Test URLs ---

* http://localhost:8181/{SERVICE}.svc/?$format=json
* http://localhost:8181/{SERVICE}.svc/Orders()?$format=json&$top=0&$inlinecount=allpages
* http://localhost:8181/{SERVICE}.svc/Customers()?$format=json&$orderby=CustomerID&$top=3&$select=CustomerID,ContactName,CompanyName
* http://localhost:8181/{SERVICE}.svc/Orders()?$format=json&$orderby=OrderID desc&$top=3&$select=OrderID,CustomerID,ShipName,ShipCity,ShipCountry
* http://localhost:8181/{SERVICE}.svc/Orders()?$format=json&$orderby=OrderID&$filter=OrderDate eq null&$expand=Customer&$select=OrderID,CustomerID,OrderDate,ShippedDate,Freight
* http://localhost:8181/{SERVICE}.svc/Orders()?$format=json&$orderby=OrderID&$filter=ShippedDate eq null&$expand=Customer&$select=OrderID,CustomerID,OrderDate,ShippedDate,Freight
* http://localhost:8181/{SERVICE}.svc/Orders()?$format=json&$orderby=OrderID&$filter=Freight eq null&$expand=Customer&$select=OrderID,CustomerID,OrderDate,ShippedDate,Freight
* http://localhost:8181/{SERVICE}.svc/Customers('ALFKI')?$format=json&$expand=Orders&$select=CustomerID,ContactName,CompanyName,Orders/OrderID,Orders/ShipName,Orders/ShipCity,Orders/ShipCountry
* http://localhost:8181/{SERVICE}.svc/Orders()?$format=json&$orderby=OrderID&$top=3&$expand=Customer&$select=OrderID,CustomerID,Customer/ContactName,Customer/CompanyName
* http://localhost:8181/{SERVICE}.svc/Orders()?$format=json&$orderby=OrderID&$top=3&$expand=Customer&$select=OrderID,CustomerID,Customer/ContactName,Customer/CompanyName
