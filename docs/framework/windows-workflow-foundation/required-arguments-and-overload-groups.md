---
title: Обязательные аргументы и группы перегруженных аргументов
ms.date: 03/30/2017
ms.assetid: 4ca3ed06-b9af-4b85-8b70-88c2186aefa3
ms.openlocfilehash: d7cfe00d93f1eede77bcda5881c63843722c9a17
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452905"
---
# <a name="required-arguments-and-overload-groups"></a><span data-ttu-id="3c8d7-102">Обязательные аргументы и группы перегруженных аргументов</span><span class="sxs-lookup"><span data-stu-id="3c8d7-102">Required Arguments and Overload Groups</span></span>
<span data-ttu-id="3c8d7-103">Действия можно настроить таким образом, чтобы для их выполнения требовалась привязка определенных аргументов.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-103">Activities can be configured so that certain arguments are required to be bound for the activity to be valid for execution.</span></span> <span data-ttu-id="3c8d7-104">Атрибут `RequiredArgument` указывает, что для действия необходимы определенные аргументы, а атрибут `OverloadGroup` используется для группирования категорий необходимых аргументов.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-104">The `RequiredArgument` attribute is used to indicate that certain arguments on an activity are required and the `OverloadGroup` attribute is used to group categories of required arguments together.</span></span> <span data-ttu-id="3c8d7-105">С помощью атрибутов авторы действий могут реализовать простые или сложные конфигурации проверки правильности действий.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-105">By using the attributes, activity authors can provide simple or complex activity validation configurations.</span></span>  
  
## <a name="using-required-arguments"></a><span data-ttu-id="3c8d7-106">Использование обязательных аргументов</span><span class="sxs-lookup"><span data-stu-id="3c8d7-106">Using Required Arguments</span></span>  
 <span data-ttu-id="3c8d7-107">Чтобы использовать атрибут `RequiredArgument` в действии, укажите необходимые аргументы с помощью <xref:System.Activities.RequiredArgumentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-107">To use the `RequiredArgument` attribute in an activity, indicate the desired arguments using <xref:System.Activities.RequiredArgumentAttribute>.</span></span> <span data-ttu-id="3c8d7-108">В этом примере действие `Add` определено, как имеющее два обязательных аргумента.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-108">In this example, an `Add` activity is defined that has two required arguments.</span></span>  
  
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
  
 <span data-ttu-id="3c8d7-109">В XAML необходимые аргументы также обозначаются с помощью <xref:System.Activities.RequiredArgumentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-109">In XAML, required arguments are also indicated by using <xref:System.Activities.RequiredArgumentAttribute>.</span></span> <span data-ttu-id="3c8d7-110">В данном примере действие `Add` определено с помощью трех аргументов и использует действие <xref:System.Activities.Statements.Assign%601> для выполнения операции сложения.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-110">In this example the `Add` activity is defined by using three arguments and uses an <xref:System.Activities.Statements.Assign%601> activity to perform the add operation.</span></span>  
  
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
  
 <span data-ttu-id="3c8d7-111">При использовании действия, если любой из необходимых аргументов не привязан, будет возвращена следующая ошибка проверки.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-111">If the activity is used and either of the required arguments is not bound the following validation error is returned.</span></span>  
  
 <span data-ttu-id="3c8d7-112">**Не указано значение необходимого аргумента действия «Операнд1».**</span><span class="sxs-lookup"><span data-stu-id="3c8d7-112">**Value for a required activity argument 'Operand1' was not supplied.**</span></span>  
> [!NOTE]
> <span data-ttu-id="3c8d7-113">Дополнительные сведения о проверке и обработке ошибок и предупреждений проверки, см. в разделе [вызов проверки действия](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md).</span><span class="sxs-lookup"><span data-stu-id="3c8d7-113">For more information about checking for and handling validation errors and warnings, see [Invoking Activity Validation](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md).</span></span>  
  
## <a name="using-overload-groups"></a><span data-ttu-id="3c8d7-114">Использование групп перегрузки</span><span class="sxs-lookup"><span data-stu-id="3c8d7-114">Using Overload Groups</span></span>

<span data-ttu-id="3c8d7-115">Группы перегрузки предоставляют метод, позволяющий определить, какие комбинации аргументов допустимы для действия.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-115">Overload groups provide a method for indicating which combinations of arguments are valid in an activity.</span></span> <span data-ttu-id="3c8d7-116">Аргументы группируются с помощью <xref:System.Activities.OverloadGroupAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-116">Arguments are grouped together by using <xref:System.Activities.OverloadGroupAttribute>.</span></span> <span data-ttu-id="3c8d7-117">Каждой группе присваивается имя, которое задается параметром <xref:System.Activities.OverloadGroupAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-117">Each group is given a name that is specified by the <xref:System.Activities.OverloadGroupAttribute>.</span></span> <span data-ttu-id="3c8d7-118">Действие является допустимым, если только один набор аргументов в группе перегрузки привязаны.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-118">The activity is valid when only one set of arguments in an overload group are bound.</span></span> <span data-ttu-id="3c8d7-119">В следующем примере определяется класс `CreateLocation`.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-119">In the following example, a `CreateLocation` class is defined.</span></span>  
  
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
  
 <span data-ttu-id="3c8d7-120">Задача данного действия - указать местоположение в США.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-120">The objective of this activity is to specify a location in the US.</span></span> <span data-ttu-id="3c8d7-121">Для этого пользователь действия может указать местоположение с помощью одной из трех групп аргументов.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-121">To do this, the user of the activity can specify the location using one of three groups of arguments.</span></span> <span data-ttu-id="3c8d7-122">Чтобы указать допустимые сочетания аргументов, определены 3 группы перегрузки.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-122">To specify the valid combinations of arguments, three overload groups are defined.</span></span> <span data-ttu-id="3c8d7-123">`G1` содержит аргументы `Latitude` и `Longitude`.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-123">`G1` contains the `Latitude` and `Longitude` arguments.</span></span> <span data-ttu-id="3c8d7-124">`G2` содержит `Street`, `City` и `State`.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-124">`G2` contains `Street`, `City`, and `State`.</span></span> <span data-ttu-id="3c8d7-125">`G3` содержит `Street` и `Zip`.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-125">`G3` contains `Street` and `Zip`.</span></span> <span data-ttu-id="3c8d7-126">`Name` также является обязательным аргументом, но не входит в группу перегрузки.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-126">`Name` is also a required argument, but it is not part of an overload group.</span></span> <span data-ttu-id="3c8d7-127">Чтобы данное действие было допустимым, `Name` должно быть привязано вместе со всеми аргументами только из одной группы перегрузки.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-127">For this activity to be valid, `Name` would have to be bound together with all of the arguments from one and only one overload group.</span></span>  
  
 <span data-ttu-id="3c8d7-128">В следующем примере, взятом из [действия доступа к базе данных](../../../docs/framework/windows-workflow-foundation/samples/database-access-activities.md) образца имеется 2 группы перегрузки: `ConnectionString` и `ConfigFileSectionName`.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-128">In the following example, taken from the [Database Access Activities](../../../docs/framework/windows-workflow-foundation/samples/database-access-activities.md) sample, there are two overload groups: `ConnectionString` and `ConfigFileSectionName`.</span></span> <span data-ttu-id="3c8d7-129">Чтобы данное действие было допустимым, должны быть связаны либо аргументы `ProviderName` и `ConnectionString`, либо аргумент `ConfigName`, но не оба.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-129">For this activity to be valid, either the `ProviderName` and `ConnectionString` arguments must be bound, or the `ConfigName` argument, but not both.</span></span>  
  
```  
Public class DbUpdate: AsyncCodeActivity  
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
  
 <span data-ttu-id="3c8d7-130">При определении группы перегрузки:</span><span class="sxs-lookup"><span data-stu-id="3c8d7-130">When defining an overload group:</span></span>  
  
-   <span data-ttu-id="3c8d7-131">Группа перегрузки не может быть подмножеством или эквивалентным набором другой группы перегрузки.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-131">An overload group cannot be a subset or an equivalent set of another overload group.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3c8d7-132">Существует одно исключение из данного правила.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-132">There is one exception to this rule.</span></span> <span data-ttu-id="3c8d7-133">Если группа перегрузки является подмножеством другой группы перегрузки и подмножество содержит только аргументы, где `RequiredArgument` равен `false`, то группа перегрузки допустима.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-133">If an overload group is a subset of another overload group, and the subset contains only arguments where `RequiredArgument` is `false`, then the overload group is valid.</span></span>  
  
-   <span data-ttu-id="3c8d7-134">Группы перегрузки могут пересекаться, но это приведет к ошибке, если пересечение групп содержит все обязательные аргументы одной или обеих групп.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-134">Overload groups can overlap but it is an error if the intersection of the groups contains all the required arguments of one or both of the overload groups.</span></span> <span data-ttu-id="3c8d7-135">В предыдущем примере группы перегрузки `G2` и `G3` перекрываются, но поскольку пересечение не содержит все аргументы одной или обеих групп, то это допустимо.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-135">In the previous example the `G2` and `G3` overload groups overlapped, but because the intersection did not contain all the arguments of one or both of the groups this was valid.</span></span>  
  
 <span data-ttu-id="3c8d7-136">Если имеет место привязка аргументов в группе перегрузки:</span><span class="sxs-lookup"><span data-stu-id="3c8d7-136">When binding arguments in an overload group:</span></span>  
  
-   <span data-ttu-id="3c8d7-137">Группа перегрузки считается связанной, если все аргументы `RequiredArgument` в этой группе - связанные.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-137">An overload group is considered bound if all the `RequiredArgument` arguments in the group are bound.</span></span>  
  
-   <span data-ttu-id="3c8d7-138">Если в группе нет ни одного аргумента `RequiredArgument` и хотя бы один аргумент связан, то группа также считается связанной.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-138">If a group has zero `RequiredArgument` arguments and at least one argument bound, then the group is considered bound.</span></span>  
  
-   <span data-ttu-id="3c8d7-139">Возникает ошибка проверки, если ни одна из групп перегрузки не является связанной и при этом нет ни одной группы перегрузки без аргументов `RequiredArgument`.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-139">It is a validation error if no overload groups are bound unless one overload group has no `RequiredArgument` arguments in it.</span></span>  
  
-   <span data-ttu-id="3c8d7-140">При наличии нескольких привязанных групп перегрузки возникнет ошибка, т. е. все обязательные аргументы в одной группе являются связанными и любой аргумент в другой группе перегрузки также связан.</span><span class="sxs-lookup"><span data-stu-id="3c8d7-140">It is an error to have more than one overload group bound, that is, all required arguments in one overload group are bound and any argument in another overload group is also bound.</span></span>
