---
title: Обязательные аргументы и группы перегруженных аргументов
ms.date: 03/30/2017
ms.assetid: 4ca3ed06-b9af-4b85-8b70-88c2186aefa3
ms.openlocfilehash: 4eb62306f52b8ff890d5a5333c3789bd84ad7f60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142944"
---
# <a name="required-arguments-and-overload-groups"></a>Обязательные аргументы и группы перегруженных аргументов
Действия можно настроить таким образом, чтобы для их выполнения требовалась привязка определенных аргументов. Атрибут `RequiredArgument` указывает, что для действия необходимы определенные аргументы, а атрибут `OverloadGroup` используется для группирования категорий необходимых аргументов. С помощью атрибутов авторы действий могут реализовать простые или сложные конфигурации проверки правильности действий.  
  
## <a name="using-required-arguments"></a>Использование обязательных аргументов  
 Чтобы использовать атрибут `RequiredArgument` в действии, укажите необходимые аргументы с помощью <xref:System.Activities.RequiredArgumentAttribute>. В этом примере действие `Add` определено, как имеющее два обязательных аргумента.  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 В XAML необходимые аргументы также обозначаются с помощью <xref:System.Activities.RequiredArgumentAttribute>. В данном примере действие `Add` определено с помощью трех аргументов и использует действие <xref:System.Activities.Statements.Assign%601> для выполнения операции сложения.  
  
```xaml  
<Activity x:Class="ValidationDemo.Add" ...>  
  <x:Members>  
    <x:Property Name="Operand1" Type="InArgument(x:Int32)">  
      <x:Property.Attributes>  
        <RequiredArgumentAttribute />  
      </x:Property.Attributes>  
    </x:Property>  
    <x:Property Name="Operand2" Type="InArgument(x:Int32)">  
      <x:Property.Attributes>  
        <RequiredArgumentAttribute />  
      </x:Property.Attributes>  
    </x:Property>  
    <x:Property Name="Result" Type="OutArgument(x:Int32)" />  
  </x:Members>  
  <Assign>  
    <Assign.To>  
      <OutArgument x:TypeArguments="x:Int32">[Result]</OutArgument>  
    </Assign.To>  
    <Assign.Value>  
      <InArgument x:TypeArguments="x:Int32">[Operand1 + Operand2]</InArgument>  
    </Assign.Value>  
  </Assign>  
</Activity>  
```  
  
 При использовании действия, если любой из необходимых аргументов не привязан, будет возвращена следующая ошибка проверки.  
  
 **Не указано значение необходимого аргумента действия Operand1.**  
> [!NOTE]
> Для получения дополнительной информации о проверке и [Invoking Activity Validation](invoking-activity-validation.md)обработке ошибок и предупреждений проверки, см.  
  
## <a name="using-overload-groups"></a>Использование групп перегрузки

Группы перегрузки предоставляют метод, позволяющий определить, какие комбинации аргументов допустимы для действия. Аргументы группируются с помощью <xref:System.Activities.OverloadGroupAttribute>. Каждой группе дается имя, <xref:System.Activities.OverloadGroupAttribute>указанное . Действие действительно, когда связан только один набор аргументов в группе перегрузок. В следующем примере определяется класс `CreateLocation`.  
  
```csharp  
class CreateLocation: Activity  
{  
    [RequiredArgument]  
    public InArgument<string> Name { get; set; }  
  
    public InArgument<string> Description { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G1")]  
    public InArgument<int> Latitude { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G1")]  
    public InArgument<int> Longitude { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    [OverloadGroup("G3")]  
    public InArgument<string> Street { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    public InArgument<string> City { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    public InArgument<string> State { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G3")]  
    public InArgument<int> Zip { get; set; }
}  
```  
  
 Задача данного действия - указать местоположение в США. Для этого пользователь действия может указать местоположение с помощью одной из трех групп аргументов. Чтобы указать допустимые сочетания аргументов, определены 3 группы перегрузки. `G1` содержит аргументы `Latitude` и `Longitude`. `G2` содержит `Street`, `City` и `State`. `G3` содержит `Street` и `Zip`. `Name` также является обязательным аргументом, но не входит в группу перегрузки. Чтобы данное действие было допустимым, `Name` должно быть привязано вместе со всеми аргументами только из одной группы перегрузки.  
  
 В следующем примере, взятом из выборки [деятельности по доступу к базе данных,](./samples/database-access-activities.md) есть две группы перегрузок: `ConnectionString` и `ConfigFileSectionName`. Чтобы данное действие было допустимым, должны быть связаны либо аргументы `ProviderName` и `ConnectionString`, либо аргумент `ConfigName`, но не оба.  
  
```csharp  
public class DbUpdate: AsyncCodeActivity  
{  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
  
    [DependsOn("Parameters")]  
    public OutArgument<int> AffectedRecords { get; set; }
}  
```  
  
 При определении группы перегрузки:  
  
- Группа перегрузки не может быть подмножеством или эквивалентным набором другой группы перегрузки.  
  
    > [!NOTE]
    > Существует одно исключение из данного правила. Если группа перегрузки является подмножеством другой группы перегрузки и подмножество содержит только аргументы, где `RequiredArgument` равен `false`, то группа перегрузки допустима.  
  
- Группы перегрузки могут пересекаться, но это приведет к ошибке, если пересечение групп содержит все обязательные аргументы одной или обеих групп. В предыдущем примере группы перегрузки `G2` и `G3` перекрываются, но поскольку пересечение не содержит все аргументы одной или обеих групп, то это допустимо.  
  
 Если имеет место привязка аргументов в группе перегрузки:  
  
- Группа перегрузки считается связанной, если все аргументы `RequiredArgument` в этой группе - связанные.  
  
- Если в группе нет ни одного аргумента `RequiredArgument` и хотя бы один аргумент связан, то группа также считается связанной.  
  
- Возникает ошибка проверки, если ни одна из групп перегрузки не является связанной и при этом нет ни одной группы перегрузки без аргументов `RequiredArgument`.  
  
- При наличии нескольких привязанных групп перегрузки возникнет ошибка, т. е. все обязательные аргументы в одной группе являются связанными и любой аргумент в другой группе перегрузки также связан.
