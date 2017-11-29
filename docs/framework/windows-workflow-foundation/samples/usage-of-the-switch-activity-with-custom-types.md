---
title: "Использование действия Switch с пользовательскими типами"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 482a48c4-eb83-40c3-a4e2-2f9a8af88b75
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a8a4418c582d00f1163305ce5d63c63c198dbc30
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="usage-of-the-switch-activity-with-custom-types"></a><span data-ttu-id="882cf-102">Использование действия Switch с пользовательскими типами</span><span class="sxs-lookup"><span data-stu-id="882cf-102">Usage of the Switch Activity with Custom Types</span></span>
<span data-ttu-id="882cf-103">В этом примере описывается включение <!--zz <xref:System.Activities. Statements.Switch`1>--> `xref:System.Activities` Statements.Switch`1?qualifyHint=False&autoUpgrade=True activity to evaluate a user-defined complex type at runtime. In most traditional procedural programming languages, a [switch](http://go.microsoft.com/fwlink/?LinkId=180521) statement selects an execution logic based on the conditional evaluation of a variable. Traditionally, a \`переключение "инструкция работает на выражение, которое может быть оценено статически.</span><span class="sxs-lookup"><span data-stu-id="882cf-103">This sample describes how to enable a <!--zz <xref:System.Activities. Statements.Switch`1>--> `xref:System.Activities` Statements.Switch`1?qualifyHint=False&autoUpgrade=True activity to evaluate a user-defined complex type at runtime. In most traditional procedural programming languages, a [switch](http://go.microsoft.com/fwlink/?LinkId=180521) statement selects an execution logic based on the conditional evaluation of a variable. Traditionally, a `switch` statement operates on an expression that can be statically evaluated.</span></span> <span data-ttu-id="882cf-104">Например, в C# это означает, что поддерживаются только примитивные типы, такие как <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String> и типы перечисления.</span><span class="sxs-lookup"><span data-stu-id="882cf-104">For example, in C# this means that only primitive types, such as <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String>, and enumeration types are supported.</span></span>  
  
 <span data-ttu-id="882cf-105">Для поддержки переключения для пользовательского класса необходимо реализовать логику, которая оценивает значения пользовательского сложного типа во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="882cf-105">To enable switching on a custom class, logic must be implemented to evaluate values of the custom complex type at runtime.</span></span> <span data-ttu-id="882cf-106">Этот образец демонстрирует, реализацию переключения по пользовательскому сложному типу, называемому `Person`.</span><span class="sxs-lookup"><span data-stu-id="882cf-106">This sample demonstrates how to enable switching on a custom complex type named `Person`.</span></span>  
  
-   <span data-ttu-id="882cf-107">В пользовательском классе атрибут `Person`, a <xref:System.ComponentModel.TypeConverter> объявлен с именем пользовательского объекта <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="882cf-107">In the custom class `Person`, a <xref:System.ComponentModel.TypeConverter> attribute is declared with the name of the custom <xref:System.ComponentModel.TypeConverter>.</span></span>  
  
    ```  
    [TypeConverter(typeof(PersonConverter))]  
    public class Person  
    {  
       public string Name { get; set; }  
       public int Age { get; set; }  
    ...  
    ```  
  
-   <span data-ttu-id="882cf-108">В пользовательском классе `Person` переопределены классы <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A>.</span><span class="sxs-lookup"><span data-stu-id="882cf-108">In the custom class `Person`, the <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> classes are overridden.</span></span>  
  
    ```  
    public override bool Equals(object obj)  
    {  
        Person person = obj as Person;  
  
        if (person != null)  
        {  
            return string.Equals(this.Name, person.Name);  
        }  
  
        return false;  
    }  
  
    public override int GetHashCode()  
    {  
        if (this.Name != null)  
        {  
            return this.Name.GetHashCode();  
        }  
  
        return 0;  
    }  
    ```  
  
-   <span data-ttu-id="882cf-109">Реализован пользовательский класс <xref:System.ComponentModel.TypeConverter>, который выполняет преобразование экземпляра пользовательского класса в строку, а строки - в экземпляр пользовательского класса.</span><span class="sxs-lookup"><span data-stu-id="882cf-109">A custom <xref:System.ComponentModel.TypeConverter> class is implemented that performs the conversion of an instance of the custom class to a string and a string to an instance of a custom class.</span></span>  
  
    ```  
    public class PersonConverter : TypeConverter  
    {  
        public override bool CanConvertFrom(ITypeDescriptorContext context,  
           Type sourceType)  
        {  
            return (sourceType is string);  
        }  
  
        // Overrides the ConvertFrom method of TypeConverter.  
        public override object ConvertFrom(ITypeDescriptorContext context,  
           CultureInfo culture, object value)  
        {  
            if (value == null)  
            {  
                return null;  
            }  
  
            if (value is string)  
            {  
                return new Person  
                {  
                    Name = (string)value  
                };  
            }  
  
            return base.ConvertFrom(context, culture, value);  
        }  
  
        // Overrides the ConvertTo method of TypeConverter.  
        public override object ConvertTo(ITypeDescriptorContext context,  
           CultureInfo culture, object value, Type destinationType)  
        {  
            if (destinationType == typeof(string))  
            {  
                if (value != null)  
                {  
                    return ((Person) value).Name;  
                }  
                else  
                {  
                    return null;  
                }  
            }  
  
            return base.ConvertTo(context, culture, value, destinationType);  
        }  
    }  
    ```  
  
 <span data-ttu-id="882cf-110">В этот образец включены следующие файлы.</span><span class="sxs-lookup"><span data-stu-id="882cf-110">The following files are included in this sample:</span></span>  
  
-   <span data-ttu-id="882cf-111">**Person.cs**: определяет `Person` класса.</span><span class="sxs-lookup"><span data-stu-id="882cf-111">**Person.cs**: Defines the `Person` class.</span></span>  
  
-   <span data-ttu-id="882cf-112">**PersonConverter.cs**: преобразователь типов для `Person` класса.</span><span class="sxs-lookup"><span data-stu-id="882cf-112">**PersonConverter.cs**: The type converter for the `Person` class.</span></span>  
  
-   <span data-ttu-id="882cf-113">**Sequence.XAML**: рабочий процесс, который переключается `Person` типа.</span><span class="sxs-lookup"><span data-stu-id="882cf-113">**Sequence.xaml**: a workflow that switches over the `Person` type.</span></span>  
  
-   <span data-ttu-id="882cf-114">**Program.cs**: основная функция, которая запускает рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="882cf-114">**Program.cs**: The main function that runs the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="882cf-115">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="882cf-115">To use this sample</span></span>  
  
1.  <span data-ttu-id="882cf-116">Загрузите Switch.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="882cf-116">Load Switch.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="882cf-117">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="882cf-117">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="882cf-118">Чтобы запустить образец, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="882cf-118">Press CTRL + F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="882cf-119">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="882cf-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="882cf-120">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="882cf-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="882cf-121">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="882cf-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="882cf-122">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="882cf-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Switch`  
  
## <a name="see-also"></a><span data-ttu-id="882cf-123">См. также</span><span class="sxs-lookup"><span data-stu-id="882cf-123">See Also</span></span>  
 [<span data-ttu-id="882cf-124">Встроенная библиотека действий</span><span class="sxs-lookup"><span data-stu-id="882cf-124">Built-In Activity Library</span></span>](../../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md)
