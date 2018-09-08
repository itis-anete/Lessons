# Лекция №4
 - # ADO.NET (activex data object .net)
   - Интерфейсы доступа к данным (OLE DB, ODBC)
   - Источники данных
   - System.Data - [ADO.NET](#add1)
   - Data Mapper (Dapper)
   - Active Record
   - Unit of work
 
# Задание №3
 - Выбрать модель данных
 - Объяснить выбор модели данных
 - Реализовать модель данных через ORM
 
# Доп. материалы №1<a name="add1"></a>
![Database Schema](ADO.NET)

# Доп. материалы №2<a name="add2"></a>
 - Model
````C#
public class Dog
{
    public int? Age { get; set; }
    public Guid Id { get; set; }
    public string Name { get; set; }
    public float? Weight { get; set; }

    public int IgnoredProperty { get { return 1; } }
}
````
 - Data Mapper
````C#
var dog = connection.Query<Dog>("select Age = @Age, Id = @Id", new { Age = (int?)null, Id = Guid.NewGuid(); });
````
 - Attribute mapping (System.Data.Linq.Data.Mapping)
````C#
[Table("db_dogs")]
public class Dog
{
    [Column("c_age")]
    public int? Age { get; set; }
    
    [Column("c_id")]
    [Key]
    public Guid Id { get; set; }
    
    
    [Column("c_name")]
    public string Name { get; set; }
    
    [Column("c_weight")]
    [Meta(typeof(int))]
    public float? Weight { get; set; }

    public int IgnoredProperty { get { return 1; } }  
}
````
 - Fluent mapping
````C#
//functional mapping example
db.Table<Dog>("db_dogs")
  .Column("c_age",x=>x.Age)
  .Column("c_id",x=>x.Id)
    .AsFK();
  .Column("c_name",x=>x.Name)
  .Column("c_weight",x=>x.Weight)
    .AsType<int>();
````
