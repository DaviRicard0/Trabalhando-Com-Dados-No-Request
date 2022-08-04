# Trabalhando-Com-Dados-No-Request
<p>
app.MapGet("/", () => "Olá Mundo!");

app.MapGet("/user", () => new {Name="Davi", Age=34});

app.MapGet("/addHeader",(<b>HttpResponse</b> response)=>{
    response.Headers.Add("Teste","Davi");
    return new {Name="Davi", Age=34};
});

app.MapPost("/produto",(<b>Product</b> product)=>{
    return product;
});

app.MapGet("/produto",(<b>[FromQuery]</b> DateTime dateStart,<b>[FromQuery]</b> DateTime dateEnd)=>{
    return new {dateStart,dateEnd};
});

app.MapGet("/produto/{id}",(<b>[FromRoute]</b> int id)=>{
    return new {id};
});

app.MapGet("/produtos",(<b>HttpRequest</b> request)=>{
    return new{ ProdutoId=request.Headers["produto-id"].ToString()};
});
</p>
