---
title: "Сравнение веб-служб ASP.NET с веб-службами на основе WCF по процессу разработки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f362d00e-ce82-484f-9d4f-27e579d5c320
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6aa79e76bd81c0d56b30d4bac2edd4b9cbef6b33
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-development"></a><span data-ttu-id="cc18d-102">Сравнение веб-служб ASP.NET с веб-службами на основе WCF по процессу разработки</span><span class="sxs-lookup"><span data-stu-id="cc18d-102">Comparing ASP.NET Web Services to WCF Based on Development</span></span>
<span data-ttu-id="cc18d-103">В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] предусмотрена возможность работы в режиме совместимости с ASP.NET, что позволяет программировать и настраивать приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] как веб-службы ASP.NET и имитировать их поведение.</span><span class="sxs-lookup"><span data-stu-id="cc18d-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] has an ASP.NET compatibility mode option to enable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications to be programmed and configured like ASP.NET Web services, and mimic their behavior.</span></span> <span data-ttu-id="cc18d-104">В следующих разделах приводится сравнение веб-служб ASP.NET и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с точки зрения того, что необходимо для разработки приложений с использованием обеих технологий.</span><span class="sxs-lookup"><span data-stu-id="cc18d-104">The following sections compare ASP.NET Web services and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] based on what is required to develop applications using both technologies.</span></span>  
  
## <a name="data-representation"></a><span data-ttu-id="cc18d-105">Представление данных</span><span class="sxs-lookup"><span data-stu-id="cc18d-105">Data Representation</span></span>  
 <span data-ttu-id="cc18d-106">Разработка веб-службы с помощью ASP.NET обычно начинается с определения сложных типов данных, которые будет использовать служба.</span><span class="sxs-lookup"><span data-stu-id="cc18d-106">The development of a Web service with ASP.NET typically begins with defining any complex data types the service is to use.</span></span> <span data-ttu-id="cc18d-107">ASP.NET предполагает использование сериализатора <xref:System.Xml.Serialization.XmlSerializer> для преобразования представленных типами .NET Framework данных в XML для передачи службе или от службы и для преобразования полученных в виде XML данных в объекты .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cc18d-107">ASP.NET relies on the <xref:System.Xml.Serialization.XmlSerializer> to translate data represented by .NET Framework types to XML for transmission to or from a service and to translate data received as XML into .NET Framework objects.</span></span> <span data-ttu-id="cc18d-108">Определение сложных типов данных, которые будет использовать служба ASP.NET, требует определения классов .NET Framework, которые <xref:System.Xml.Serialization.XmlSerializer> может сериализовать в XML и из XML.</span><span class="sxs-lookup"><span data-stu-id="cc18d-108">Defining the complex data types that an ASP.NET service is to use requires the definition of .NET Framework classes that the <xref:System.Xml.Serialization.XmlSerializer> can serialize to and from XML.</span></span> <span data-ttu-id="cc18d-109">Такие классы могут быть написаны вручную или сформированы из определений типов в схеме XML с помощью утилиты командной строки для поддержки схем XML/типов данных (xsd.exe).</span><span class="sxs-lookup"><span data-stu-id="cc18d-109">Such classes can be written manually, or generated from definitions of the types in XML Schema using the command-line XML Schemas/Data Types Support Utility, xsd.exe.</span></span>  
  
 <span data-ttu-id="cc18d-110">Ниже перечислены основные моменты, которые необходимо знать для определения классов .NET Framework, которые <xref:System.Xml.Serialization.XmlSerializer> сможет сериализовать в XML и из XML.</span><span class="sxs-lookup"><span data-stu-id="cc18d-110">The following is a list of key issues to know when defining .NET Framework classes that the <xref:System.Xml.Serialization.XmlSerializer> can serialize to and from XML:</span></span>  
  
-   <span data-ttu-id="cc18d-111">В XML преобразуются только открытые поля и свойства объектов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cc18d-111">Only the public fields and properties of .NET Framework objects are translated into XML.</span></span>  
  
-   <span data-ttu-id="cc18d-112">Экземпляры классов коллекций могут быть сериализованы в XML только при условии реализации классами интерфейса <xref:System.Collections.IEnumerable> или <xref:System.Collections.ICollection>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-112">Instances of collection classes can be serialized into XML only if the classes implement either the <xref:System.Collections.IEnumerable> or <xref:System.Collections.ICollection> interface.</span></span>  
  
-   <span data-ttu-id="cc18d-113">Классы, реализующие интерфейс <xref:System.Collections.IDictionary>, такие как <xref:System.Collections.Hashtable>, не могут быть сериализованы в XML.</span><span class="sxs-lookup"><span data-stu-id="cc18d-113">Classes that implement the <xref:System.Collections.IDictionary> interface, such as <xref:System.Collections.Hashtable>, cannot be serialized into XML.</span></span>  
  
-   <span data-ttu-id="cc18d-114">Пространство имен <xref:System.Xml.Serialization> содержит огромное множество типов атрибутов, которые можно добавлять в классы .NET Framework и их члены для управления тем, как экземпляры класса будут представлены в XML.</span><span class="sxs-lookup"><span data-stu-id="cc18d-114">The great many attribute types in the <xref:System.Xml.Serialization> namespace can be added to a .NET Framework class and its members to control how instances of the class are represented in XML.</span></span>  
  
 <span data-ttu-id="cc18d-115">Разработка приложений для [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обычно также начинается с определения сложных типов.</span><span class="sxs-lookup"><span data-stu-id="cc18d-115">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application development usually also begins with the definition of complex types.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc18d-116"> может использовать те же типы .NET Framework, что и веб-службы ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc18d-116"> can be made to use the same .NET Framework types as ASP.NET Web services.</span></span>  
  
 <span data-ttu-id="cc18d-117">В типы .NET Framework можно добавлять атрибуты [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, чтобы указать, что экземпляры типа должны сериализоваться в XML, а также какие конкретные поля или свойства типа должны быть сериализованы, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="cc18d-117">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> can be added to .NET Framework types to indicate that instances of the type are to be serialized into XML, and which particular fields or properties of the type are to be serialized, as shown in the following sample code.</span></span>  
  
```  
//Example One:   
[DataContract]  
public class LineItem  
{  
    [DataMember]  
    public string ItemNumber;  
    [DataMember]  
    public decimal Quantity;  
    [DataMember]  
    public decimal UnitPrice;  
}  
  
//Example Two:   
public class LineItem  
{  
    [DataMember]  
    private string itemNumber;  
    [DataMember]  
    private decimal quantity;  
    [DataMember]  
    private decimal unitPrice;  
  
    public string ItemNumber  
    {  
      get  
      {  
          return this.itemNumber;  
      }  
  
      set  
      {  
          this.itemNumber = value;  
      }  
    }  
  
    public decimal Quantity  
    {  
        get  
        {  
            return this.quantity;  
        }  
  
        set  
        {  
            this.quantity = value;  
        }  
    }  
  
    public decimal UnitPrice  
    {  
      get  
      {  
          return this.unitPrice;  
      }  
  
      set  
      {  
          this.unitPrice = value;  
      }  
    }  
}  
  
//Example Three:   
public class LineItem  
{  
     private string itemNumber;  
     private decimal quantity;  
     private decimal unitPrice;  
  
     [DataMember]  
     public string ItemNumber  
     {  
       get  
       {  
          return this.itemNumber;  
       }  
  
       set  
       {  
           this.itemNumber = value;  
       }  
     }  
  
     [DataMember]  
     public decimal Quantity  
     {  
          get  
          {  
              return this.quantity;  
          }  
  
          set  
          {  
             this.quantity = value;  
          }  
     }  
  
     [DataMember]  
     public decimal UnitPrice  
     {  
          get  
          {  
              return this.unitPrice;  
          }  
  
          set  
          {  
              this.unitPrice = value;  
          }  
     }  
}  
```  
  
 <span data-ttu-id="cc18d-118">Атрибут <xref:System.Runtime.Serialization.DataContractAttribute> означает, что ноль или более полей или свойств типа должны быть сериализованы, тогда как атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> указывает, что определенное поле или свойство должно быть сериализовано.</span><span class="sxs-lookup"><span data-stu-id="cc18d-118">The <xref:System.Runtime.Serialization.DataContractAttribute> signifies that zero or more of a type’s fields or properties are to be serialized, while the <xref:System.Runtime.Serialization.DataMemberAttribute> indicates that a particular field or property is to be serialized.</span></span> <span data-ttu-id="cc18d-119">Атрибут <xref:System.Runtime.Serialization.DataContractAttribute> может быть применен к классу или структуре.</span><span class="sxs-lookup"><span data-stu-id="cc18d-119">The <xref:System.Runtime.Serialization.DataContractAttribute> can be applied to a class or structure.</span></span> <span data-ttu-id="cc18d-120">Атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> может быть применен к полю или свойству, причем поля и свойства, к которым применяется атрибут, могут быть как открытыми, так и закрытыми.</span><span class="sxs-lookup"><span data-stu-id="cc18d-120">The <xref:System.Runtime.Serialization.DataMemberAttribute> can be applied to a field or a property, and the fields and properties to which the attribute is applied can be either public or private.</span></span> <span data-ttu-id="cc18d-121">Экземпляры типов, к которым применен атрибут <xref:System.Runtime.Serialization.DataContractAttribute>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] называются контрактами данных.</span><span class="sxs-lookup"><span data-stu-id="cc18d-121">Instances of types that have the <xref:System.Runtime.Serialization.DataContractAttribute> applied to them are referred to as data contracts in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="cc18d-122">Они сериализуются в XML с помощью сериализатора <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-122">They are serialized into XML using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="cc18d-123">Ниже перечислены важные различия между использованием сериализатора <xref:System.Runtime.Serialization.DataContractSerializer> и использованием сериализатора <xref:System.Xml.Serialization.XmlSerializer> и различных атрибутов из пространства имен <xref:System.Xml.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-123">The following is a list of the important differences between using the <xref:System.Runtime.Serialization.DataContractSerializer> and using the <xref:System.Xml.Serialization.XmlSerializer> and the various attributes of the <xref:System.Xml.Serialization> namespace.</span></span>  
  
-   <span data-ttu-id="cc18d-124">Сериализатор <xref:System.Xml.Serialization.XmlSerializer> и атрибуты из пространства имен <xref:System.Xml.Serialization> предназначены для того, чтобы разработчик мог сопоставлять типы .NET Framework с любым допустимым типом, определенным в схеме XML, и как таковые позволяют очень точно управлять тем, как тип будет представлен в XML.</span><span class="sxs-lookup"><span data-stu-id="cc18d-124">The <xref:System.Xml.Serialization.XmlSerializer> and the attributes of the <xref:System.Xml.Serialization> namespace are designed to allow you to map .NET Framework types to any valid type defined in XML Schema, and so they provide for very precise control over how a type is represented in XML.</span></span> <span data-ttu-id="cc18d-125">Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> и атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute> позволяют контролировать представление типа в XML в очень небольшой степени.</span><span class="sxs-lookup"><span data-stu-id="cc18d-125">The <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> provide very little control over how a type is represented in XML.</span></span> <span data-ttu-id="cc18d-126">Можно указать только пространства имен и имена, используемые для представления типа и его полей или свойств в XML, а также последовательности, в которой поля и свойства будут идти в XML.</span><span class="sxs-lookup"><span data-stu-id="cc18d-126">You can only specify the namespaces and names used to represent the type and its fields or properties in the XML, and the sequence in which the fields and properties appear in the XML:</span></span>  
  
    ```  
    [DataContract(  
    Namespace="urn:Contoso:2006:January:29",  
    Name="LineItem")]  
    public class LineItem  
    {  
         [DataMember(Name="ItemNumber",IsRequired=true,Order=0)]  
         public string itemNumber;  
         [DataMember(Name="Quantity",IsRequired=false,Order = 1)]  
         public decimal quantity;  
         [DataMember(Name="Price",IsRequired=false,Order = 2)]  
         public decimal unitPrice;  
    }  
    ```  
  
     <span data-ttu-id="cc18d-127">Все остальные аспекты структуры XML-данных, используемых для представления типа .NET, определяет <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-127">Everything else about the structure of the XML used to represent the .NET type is determined by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
-   <span data-ttu-id="cc18d-128">Благодаря ограниченности контроля разработчика над представлением типа в XML процесс сериализации с помощью <xref:System.Runtime.Serialization.DataContractSerializer> весьма предсказуем и, следовательно, его легче оптимизировать.</span><span class="sxs-lookup"><span data-stu-id="cc18d-128">By not permitting much control over how a type is to be represented in XML, the serialization process becomes highly predictable for the <xref:System.Runtime.Serialization.DataContractSerializer>, and, thereby, easier to optimize.</span></span> <span data-ttu-id="cc18d-129">Практическое преимущество такого принципа работы <xref:System.Runtime.Serialization.DataContractSerializer> состоит в повышении производительности примерно на десять процентов.</span><span class="sxs-lookup"><span data-stu-id="cc18d-129">A practical benefit of the design of the <xref:System.Runtime.Serialization.DataContractSerializer> is better performance, approximately ten percent better performance.</span></span>  
  
-   <span data-ttu-id="cc18d-130">Атрибуты, предназначенные для использования в сочетании с сериализатором <xref:System.Xml.Serialization.XmlSerializer>, не указывают, какие поля или свойства сериализуются в XML, тогда как атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>, предназначенный для использования в сочетании с сериализатором <xref:System.Runtime.Serialization.DataContractSerializer>, явно показывает, какие поля или свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="cc18d-130">The attributes for use with the <xref:System.Xml.Serialization.XmlSerializer> do not indicate which fields or properties of the type are serialized into XML, whereas the <xref:System.Runtime.Serialization.DataMemberAttribute> for use with the <xref:System.Runtime.Serialization.DataContractSerializer> shows explicitly which fields or properties are serialized.</span></span> <span data-ttu-id="cc18d-131">Следовательно, контракты данных представляют собой явные контракты о структуре данных, которые будет отправлять и получать приложение.</span><span class="sxs-lookup"><span data-stu-id="cc18d-131">Therefore, data contracts are explicit contracts about the structure of the data that an application is to send and receive.</span></span>  
  
-   <span data-ttu-id="cc18d-132">Сериализатор <xref:System.Xml.Serialization.XmlSerializer> может преобразовывать в XML только открытые члены объекта .NET; сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> может преобразовывать в XML члены объектов независимо от модификаторов доступа этих членов.</span><span class="sxs-lookup"><span data-stu-id="cc18d-132">The <xref:System.Xml.Serialization.XmlSerializer> can only translate the public members of a .NET object into XML, the <xref:System.Runtime.Serialization.DataContractSerializer> can translate the members of objects into XML regardless of the access modifiers of those members.</span></span>  
  
-   <span data-ttu-id="cc18d-133">Вследствие способности сериализовать в XML закрытые члены типов для сериализатора <xref:System.Runtime.Serialization.DataContractSerializer> характерно меньшее количество ограничений на типы .NET, которые он может сериализовать в XML.</span><span class="sxs-lookup"><span data-stu-id="cc18d-133">As a consequence of being able to serialize the non-public members of types into XML, the <xref:System.Runtime.Serialization.DataContractSerializer> has fewer restrictions on the variety of .NET types that it can serialize into XML.</span></span> <span data-ttu-id="cc18d-134">В частности, он способен преобразовывать в XML такие типы, как <xref:System.Collections.Hashtable>, который реализует интерфейс <xref:System.Collections.IDictionary>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-134">In particular, it can translate into XML types like <xref:System.Collections.Hashtable> that implement the <xref:System.Collections.IDictionary> interface.</span></span> <span data-ttu-id="cc18d-135">Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> со значительно большей вероятностью сможет сериализовать в XML экземпляры любого уже существующего типа .NET без внесения в тип изменений или разработки для него оболочки.</span><span class="sxs-lookup"><span data-stu-id="cc18d-135">The <xref:System.Runtime.Serialization.DataContractSerializer> is much more likely to be able to serialize the instances of any pre-existing .NET type into XML without having to either modify the definition of the type or develop a wrapper for it.</span></span>  
  
-   <span data-ttu-id="cc18d-136">Другим следствием способности сериализатора <xref:System.Runtime.Serialization.DataContractSerializer> получать доступ к закрытым членам типа является то, что ему требуется полное доверие, тогда как сериализатор <xref:System.Xml.Serialization.XmlSerializer> этого не требует.</span><span class="sxs-lookup"><span data-stu-id="cc18d-136">Another consequence of the <xref:System.Runtime.Serialization.DataContractSerializer> being able to access the non-public members of a type is that it requires full trust, whereas the <xref:System.Xml.Serialization.XmlSerializer> does not.</span></span> <span data-ttu-id="cc18d-137">Разрешение доступа кода "полное доверие" обеспечивает полный доступ ко всем ресурсам на компьютере, к которым можно получить доступ с учетными данными, под которыми выполняется код.</span><span class="sxs-lookup"><span data-stu-id="cc18d-137">The Full Trust code access permission give complete access to all resources on a machine that can be access using the credentials under which the code is executing.</span></span> <span data-ttu-id="cc18d-138">Это разрешение следует использовать с осторожностью, поскольку полностью доверенный код имеет доступ ко всем ресурсам на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cc18d-138">This options should be used with care as fully trusted code accesses all resources on your machine.</span></span>  
  
-   <span data-ttu-id="cc18d-139">Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> предусматривает некоторую поддержку управления версиями.</span><span class="sxs-lookup"><span data-stu-id="cc18d-139">The <xref:System.Runtime.Serialization.DataContractSerializer> incorporates some support for versioning:</span></span>  
  
    -   <span data-ttu-id="cc18d-140">Атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> имеет свойство <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>, которому можно присваивать значение false для добавляемых в новые версии (т. е. отсутствовавших в предыдущих версиях) контракта данных членов, что позволяет приложениям с более новой версией контракта обрабатывать более ранние версии типа.</span><span class="sxs-lookup"><span data-stu-id="cc18d-140">The <xref:System.Runtime.Serialization.DataMemberAttribute> has an <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property that can be assigned a value of false for members that are added to new versions of a data contract that were not present in earlier versions, thereby allowing applications with the newer version of the contract to be able to process earlier versions.</span></span>  
  
    -   <span data-ttu-id="cc18d-141">Реализуя в контракте данных интерфейс <xref:System.Runtime.Serialization.IExtensibleDataObject>, разработчик может позволить сериализатору <xref:System.Runtime.Serialization.DataContractSerializer> передавать члены, определенные в более новых версиях контракта данных, через приложения с более ранними версиями контракта.</span><span class="sxs-lookup"><span data-stu-id="cc18d-141">By having a data contract implement the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface, one can allow the <xref:System.Runtime.Serialization.DataContractSerializer> to pass members defined in newer versions of a data contract through applications with earlier versions of the contract.</span></span>  
  
 <span data-ttu-id="cc18d-142">Несмотря на все различия, XML-данные, в которые <xref:System.Xml.Serialization.XmlSerializer> сериализует тип, по умолчанию семантически идентичны XML-данным, в которые сериализует тип <xref:System.Runtime.Serialization.DataContractSerializer>, при условии, что пространство имен для XML определено явным образом.</span><span class="sxs-lookup"><span data-stu-id="cc18d-142">Despite all of the differences, the XML into which the <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="cc18d-143">Следующий класс, имеющий атрибуты для использования с обоими сериализаторами, преобразуется в семантически идентичные XML-данные сериализатором <xref:System.Xml.Serialization.XmlSerializer> и сериализатором <xref:System.Runtime.Serialization.DataContractAttribute>:</span><span class="sxs-lookup"><span data-stu-id="cc18d-143">The following class, which has attributes for use with both of the serializers, are translated into semantically identical XML by the <xref:System.Xml.Serialization.XmlSerializer> and by the <xref:System.Runtime.Serialization.DataContractAttribute>:</span></span>  
  
```  
[Serializable]  
[XmlRoot(Namespace="urn:Contoso:2006:January:29")]  
[DataContract(Namespace="urn:Contoso:2006:January:29")]  
public class LineItem  
{  
     [DataMember]  
     public string ItemNumber;  
     [DataMember]  
     public decimal Quantity;  
     [DataMember]  
     public decimal UnitPrice;  
}  
```  
  
 <span data-ttu-id="cc18d-144">Пакет средств разработки программного обеспечения Windows (SDK) включает в себя программу командной строки [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Средство xsd.exe, используемое с веб-служб ASP.NET, например Svcutil.exe может создавать определения типов данных .NET из схемы XML.</span><span class="sxs-lookup"><span data-stu-id="cc18d-144">The Windows software development kit (SDK) includes a command-line tool called the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).Like the xsd.exe tool used with ASP.NET Web services, Svcutil.exe can generate definitions of .NET data types from XML Schema.</span></span> <span data-ttu-id="cc18d-145">Типы являются контрактами данных, если сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> способен выдать XML-данные в формате, определенном схемой XML; в противном случае они предназначены для сериализации с помощью <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-145">The types are data contracts if the <xref:System.Runtime.Serialization.DataContractSerializer> can emit XML in the format defined by the XML Schema; otherwise, they are intended for serialization using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="cc18d-146">С помощью Svcutil.exe также можно формировать схему XML из контрактов данных, используя для этого переключатель `/dataContractOnly`.</span><span class="sxs-lookup"><span data-stu-id="cc18d-146">The tool, Svcutil.exe, can also be made to generate XML Schema from data contracts using its `/dataContractOnly` switch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc18d-147">Хотя веб-службы ASP.NET используют сериализатор <xref:System.Xml.Serialization.XmlSerializer>, а в режиме совместимости [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с ASP.NET службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] имитируют поведение веб-служб ASP.NET, режим совместимости не означает, что можно использовать исключительно сериализатор <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-147">Although ASP.NET Web services use the <xref:System.Xml.Serialization.XmlSerializer>, and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET compatibility mode makes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services mimic the behavior of ASP.NET Web services, the ASP.NET compatibility option does not restrict one to using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="cc18d-148">Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> можно использовать и для служб, выполняемых в режиме совместимости с ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc18d-148">One can still use the <xref:System.Runtime.Serialization.DataContractSerializer> with services running in the ASP.NET compatibility mode.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="cc18d-149">Разработка служб</span><span class="sxs-lookup"><span data-stu-id="cc18d-149">Service Development</span></span>  
 <span data-ttu-id="cc18d-150">Для разработки службы с использованием ASP.NET обычно требовалось добавлять атрибут <xref:System.Web.Services.WebService> в класс и атрибут <xref:System.Web.Services.WebMethodAttribute> во все методы этого класса, которые являются операциями службы:</span><span class="sxs-lookup"><span data-stu-id="cc18d-150">To develop a service using ASP.NET, it has been customary to add the <xref:System.Web.Services.WebService> attribute to a class, and the <xref:System.Web.Services.WebMethodAttribute> to any of that class’ methods that are to be operations of the service:</span></span>  
  
```  
[WebService]  
public class Service : T:System.Web.Services.WebService  
{  
    [WebMethod]  
    public string Echo(string input)   
    {  
       return input;  
    }  
}  
```  
  
 <span data-ttu-id="cc18d-151">В ASP.NET 2.0 появилась возможность добавления атрибутов <xref:System.Web.Services.WebService> и <xref:System.Web.Services.WebMethodAttribute> в интерфейс, а не в класс, и написания класса для реализации этого интерфейса:</span><span class="sxs-lookup"><span data-stu-id="cc18d-151">ASP.NET 2.0 introduced the option of adding the attribute <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> to an interface rather than to a class, and writing a class to implement the interface:</span></span>  
  
```  
[WebService]  
public interface IEcho  
{  
    [WebMethod]  
    string Echo(string input);  
}  
  
public class Service : IEcho  
{  
  
   public string Echo(string input)  
   {  
        return input;  
    }  
}  
```  
  
 <span data-ttu-id="cc18d-152">Этот вариант является предпочтительным, так как интерфейс с атрибутом <xref:System.Web.Services.WebService> составляет контракт для операций, выполняемых службой, доступный для повторного использования в различных классах, которые могут реализовывать этот же контракт другими способами.</span><span class="sxs-lookup"><span data-stu-id="cc18d-152">Using this option is to be preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>  
  
 <span data-ttu-id="cc18d-153">Служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предоставляется путем определения одной или нескольких конечных точек [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc18d-153">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is provided by defining one or more [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoints.</span></span> <span data-ttu-id="cc18d-154">Конечная точка определяется адресом, привязкой и контрактом службы.</span><span class="sxs-lookup"><span data-stu-id="cc18d-154">An endpoint is defined by an address, a binding and a service contract.</span></span> <span data-ttu-id="cc18d-155">Адрес определяет местонахождение службы.</span><span class="sxs-lookup"><span data-stu-id="cc18d-155">The address defines where the service is located.</span></span> <span data-ttu-id="cc18d-156">Привязка задает способ обмена данными со службой.</span><span class="sxs-lookup"><span data-stu-id="cc18d-156">The binding specifies how to communicate with the service.</span></span> <span data-ttu-id="cc18d-157">Контракт службы определяет операции, которые может выполнять служба.</span><span class="sxs-lookup"><span data-stu-id="cc18d-157">The service contract defines the operations that the service can perform.</span></span>  
  
 <span data-ttu-id="cc18d-158">Контракт службы обычно определяется в первую очередь, путем добавления атрибутов <xref:System.ServiceModel.ServiceContractAttribute> и <xref:System.ServiceModel.OperationContractAttribute> в интерфейс:</span><span class="sxs-lookup"><span data-stu-id="cc18d-158">The service contract is usually defined first, by adding <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> to an interface:</span></span>  
  
```  
[ServiceContract]  
public interface IEcho  
{  
     [OperationContract]  
     string Echo(string input);  
}  
```  
  
 <span data-ttu-id="cc18d-159">Атрибут <xref:System.ServiceModel.ServiceContractAttribute> указывает, что интерфейс определяет контракт службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], а атрибут <xref:System.ServiceModel.OperationContractAttribute> указывает, какие методы интерфейса определяют операции контракта службы (если такие методы имеются).</span><span class="sxs-lookup"><span data-stu-id="cc18d-159">The <xref:System.ServiceModel.ServiceContractAttribute> specifies that the interface defines a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service contract, and the <xref:System.ServiceModel.OperationContractAttribute> indicates which, if any, of the methods of the interface define operations of the service contract.</span></span>  
  
 <span data-ttu-id="cc18d-160">После определения контракта службы он реализуется в классе - путем реализации в классе интерфейса, которым определяется контракт службы:</span><span class="sxs-lookup"><span data-stu-id="cc18d-160">Once a service contract has been defined, it is implemented in a class, by having the class implement the interface by which the service contract is defined:</span></span>  
  
```  
public class Service : IEcho  
{  
    public string Echo(string input)  
    {  
       return input;  
    }  
}  
```  
  
 <span data-ttu-id="cc18d-161">Класс, реализующий контракт службы, в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] называется типом службы.</span><span class="sxs-lookup"><span data-stu-id="cc18d-161">A class that implements a service contract is referred to as a service type in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="cc18d-162">Следующий шаг - связать адрес и привязку с типом службы.</span><span class="sxs-lookup"><span data-stu-id="cc18d-162">The next step is to associate an address and a binding with a service type.</span></span> <span data-ttu-id="cc18d-163">Это обычно делается в файле конфигурации либо путем непосредственного редактирования файла, либо с помощью редактора конфигурации, входящего в состав [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc18d-163">That is typically done in a configuration file, either by editing the file directly, or by using a configuration editor provided with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="cc18d-164">Ниже приведен пример файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cc18d-164">Here is an example of a configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
     <system.serviceModel>  
      <services>  
      <service name="Service ">  
       <endpoint   
        address="EchoService"  
        binding="basicHttpBinding"  
        contract="IEchoService "/>  
      </service>  
      </services>  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="cc18d-165">Привязка задает набор протоколов для обмена данными с приложением.</span><span class="sxs-lookup"><span data-stu-id="cc18d-165">The binding specifies the set of protocols for communicating with the application.</span></span> <span data-ttu-id="cc18d-166">В следующей таблице перечислены предоставляемые системой привязки, соответствующие стандартным вариантам.</span><span class="sxs-lookup"><span data-stu-id="cc18d-166">The following table lists the system-provided bindings that represent common options.</span></span>  
  
|<span data-ttu-id="cc18d-167">Имя</span><span class="sxs-lookup"><span data-stu-id="cc18d-167">Name</span></span>|<span data-ttu-id="cc18d-168">Назначение</span><span class="sxs-lookup"><span data-stu-id="cc18d-168">Purpose</span></span>|  
|----------|-------------|  
|<span data-ttu-id="cc18d-169">BasicHttpBinding</span><span class="sxs-lookup"><span data-stu-id="cc18d-169">BasicHttpBinding</span></span>|<span data-ttu-id="cc18d-170">Взаимодействие с веб-службами и клиентами, поддерживающими спецификации WS-BasicProfile 1.1 и Basic Security Profile 1.0.</span><span class="sxs-lookup"><span data-stu-id="cc18d-170">Interoperability with Web services and clients supporting the WS-BasicProfile 1.1 and Basic Security Profile 1.0.</span></span>|  
|<span data-ttu-id="cc18d-171">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="cc18d-171">WSHttpBinding</span></span>|<span data-ttu-id="cc18d-172">Взаимодействие с веб-службами и клиентами, поддерживающими протоколы WS-* через HTTP.</span><span class="sxs-lookup"><span data-stu-id="cc18d-172">Interoperability with Web services and clients that support the WS-* protocols over HTTP.</span></span>|  
|<span data-ttu-id="cc18d-173">WSDualHttpBinding</span><span class="sxs-lookup"><span data-stu-id="cc18d-173">WSDualHttpBinding</span></span>|<span data-ttu-id="cc18d-174">Дуплексная связь по протоколу HTTP, при которой получатель первоначального сообщения не отвечает непосредственно первоначальному отправителю, но может передавать любое количество ответов в течение некоторого периода времени, используя HTTP в соответствии с протоколами WS-*.</span><span class="sxs-lookup"><span data-stu-id="cc18d-174">Duplex HTTP communication, by which the receiver of an initial message does not reply directly to the initial sender, but may transmit any number of responses over a period of time by using HTTP in conformity with WS-* protocols.</span></span>|  
|<span data-ttu-id="cc18d-175">WSFederationBinding</span><span class="sxs-lookup"><span data-stu-id="cc18d-175">WSFederationBinding</span></span>|<span data-ttu-id="cc18d-176">Связь по протоколу HTTP, при которой доступом к ресурсам службы можно управлять на основе учетных данных, выданных явно идентифицированным поставщиком учетных данных.</span><span class="sxs-lookup"><span data-stu-id="cc18d-176">HTTP communication, in which access to the resources of a service can be controlled based on credentials issued by an explicitly-identified credential provider.</span></span>|  
|<span data-ttu-id="cc18d-177">NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="cc18d-177">NetTcpBinding</span></span>|<span data-ttu-id="cc18d-178">Безопасный, надежный, высокопроизводительный обмен данными между программными сущностями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] по сети.</span><span class="sxs-lookup"><span data-stu-id="cc18d-178">Secure, reliable, high-performance communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities across a network.</span></span>|  
|<span data-ttu-id="cc18d-179">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="cc18d-179">NetNamedPipeBinding</span></span>|<span data-ttu-id="cc18d-180">Безопасный, надежный, высокопроизводительный обмен данными между программными сущностями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], находящимися на одном и том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="cc18d-180">Secure, reliable, high-performance communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities on the same machine.</span></span>|  
|<span data-ttu-id="cc18d-181">NetMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="cc18d-181">NetMsmqBinding</span></span>|<span data-ttu-id="cc18d-182">Обмен данными между программными сущностями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с использованием очереди MSMQ.</span><span class="sxs-lookup"><span data-stu-id="cc18d-182">Communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities by using MSMQ.</span></span>|  
|<span data-ttu-id="cc18d-183">MsmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="cc18d-183">MsmqIntegrationBinding</span></span>|<span data-ttu-id="cc18d-184">Обмен данными между программной сущностью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и другой программной сущностью с использованием очереди MSMQ.</span><span class="sxs-lookup"><span data-stu-id="cc18d-184">Communication between a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entity and another software entity by using MSMQ.</span></span>|  
|<span data-ttu-id="cc18d-185">NetPeerTcpBinding</span><span class="sxs-lookup"><span data-stu-id="cc18d-185">NetPeerTcpBinding</span></span>|<span data-ttu-id="cc18d-186">Обмен данными между программными сущностями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с использованием одноранговой сети Windows.</span><span class="sxs-lookup"><span data-stu-id="cc18d-186">Communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities by using Windows Peer-to-Peer Networking.</span></span>|  
  
 <span data-ttu-id="cc18d-187">Предоставляемая системой привязка <xref:System.ServiceModel.BasicHttpBinding> включает набор протоколов, поддерживаемых веб-службами ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc18d-187">The system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>, incorporates the set of protocols supported by ASP.NET Web services.</span></span>  
  
 <span data-ttu-id="cc18d-188">Пользовательские привязки для приложений [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] легко определять как коллекции классов элементов привязки, используемых в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для реализации отдельных протоколов.</span><span class="sxs-lookup"><span data-stu-id="cc18d-188">Custom bindings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications are easily defined as collections of the binding element classes that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses to implement individual protocols.</span></span> <span data-ttu-id="cc18d-189">Можно писать новые элементы привязки для представления дополнительных протоколов.</span><span class="sxs-lookup"><span data-stu-id="cc18d-189">New binding elements can be written to represent additional protocols.</span></span>  
  
 <span data-ttu-id="cc18d-190">Внутреннее поведение типов служб можно корректировать, используя свойства семейства классов, называемых поведениями.</span><span class="sxs-lookup"><span data-stu-id="cc18d-190">The internal behavior of service types can be adjusted using the properties of a family of classes called behaviors.</span></span> <span data-ttu-id="cc18d-191">В следующем примере с помощью класса <xref:System.ServiceModel.ServiceBehaviorAttribute> указывается, что тип службы должен быть многопоточным.</span><span class="sxs-lookup"><span data-stu-id="cc18d-191">Here, the <xref:System.ServiceModel.ServiceBehaviorAttribute> class is used to specify that the service type is to be multithreaded.</span></span>  
  
```  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple]  
public class DerivativesCalculatorServiceType: IDerivativesCalculator  
```  
  
 <span data-ttu-id="cc18d-192">Некоторые поведения, такие как <xref:System.ServiceModel.ServiceBehaviorAttribute>, представляют собой атрибуты.</span><span class="sxs-lookup"><span data-stu-id="cc18d-192">Some behaviors, like <xref:System.ServiceModel.ServiceBehaviorAttribute>, are attributes.</span></span> <span data-ttu-id="cc18d-193">Другие, имеющие свойства, которые может потребоваться задавать администраторам, могут быть изменены в конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="cc18d-193">Others, the ones with properties that administrators would want to set, can be modified in the configuration of an application.</span></span>  
  
 <span data-ttu-id="cc18d-194">При программировании типов служб часто используется класс <xref:System.ServiceModel.OperationContext>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-194">In programming service types, frequent use is made of the <xref:System.ServiceModel.OperationContext> class.</span></span> <span data-ttu-id="cc18d-195">Его статическое свойство <xref:System.ServiceModel.OperationContext.Current%2A> обеспечивает доступ к информации о контексте, в котором выполняется операция.</span><span class="sxs-lookup"><span data-stu-id="cc18d-195">Its static <xref:System.ServiceModel.OperationContext.Current%2A> property provides access to information about the context in which an operation is running.</span></span> <span data-ttu-id="cc18d-196"><xref:System.ServiceModel.OperationContext> аналогичен классам <xref:System.Web.HttpContext> и <xref:System.EnterpriseServices.ContextUtil>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-196"><xref:System.ServiceModel.OperationContext> is similar to both the <xref:System.Web.HttpContext> and <xref:System.EnterpriseServices.ContextUtil> classes.</span></span>  
  
## <a name="hosting"></a><span data-ttu-id="cc18d-197">Размещение</span><span class="sxs-lookup"><span data-stu-id="cc18d-197">Hosting</span></span>  
 <span data-ttu-id="cc18d-198">Веб-службы ASP.NET компилируются в сборку библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="cc18d-198">ASP.NET Web services are compiled into a class library assembly.</span></span> <span data-ttu-id="cc18d-199">Формируется файл, называемый файлом службы, который имеет расширение ASMX и содержит директиву `@ WebService`. Эта директива идентифицирует класс, содержащий код для службы и сборку, в которой он находится.</span><span class="sxs-lookup"><span data-stu-id="cc18d-199">A file called the service file is provided that has the extension .asmx and contains an `@ WebService` directive that identifies the class that contains the code for the service and the assembly in which it is located.</span></span>  
  
```  
<%@ WebService Language="C#" Class="Service,ServiceAssembly" %>  
```  
  
 <span data-ttu-id="cc18d-200">Файл службы копируется в корень приложения ASP.NET в службах IIS, а сборка копируется в подкаталог \bin этого корня приложения.</span><span class="sxs-lookup"><span data-stu-id="cc18d-200">The service file is copied into an ASP.NET application root in Internet Information Services (IIS), and the assembly is copied into the \bin subdirectory of that application root.</span></span> <span data-ttu-id="cc18d-201">После этого приложение будет доступно по URL-адресу файла службы в корне приложения.</span><span class="sxs-lookup"><span data-stu-id="cc18d-201">The application is then accessible by using the uniform resource locator (URL) of the service file in the application root.</span></span>  
  
 <span data-ttu-id="cc18d-202">Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] могут легко быть размещены в службах IIS 5.1 или 6.0, в службе активации Windows (WAS), которая входит в состав IIS 7.0, а также в любом приложении .NET.</span><span class="sxs-lookup"><span data-stu-id="cc18d-202">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services can readily be hosted within IIS 5.1 or 6.0, the Windows Process Activation Service (WAS) that is provided as part of IIS 7.0, and within any .NET application.</span></span> <span data-ttu-id="cc18d-203">Чтобы службу можно было разместить в IIS 5.1 или 6.0, в качестве транспортного протокола связи она должна использовать HTTP.</span><span class="sxs-lookup"><span data-stu-id="cc18d-203">To host a service in IIS 5.1 or 6.0, the service must use HTTP as the communications transport protocol.</span></span>  
  
 <span data-ttu-id="cc18d-204">Чтобы разместить службу в IIS 5.1, 6.0 или в WAS, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="cc18d-204">To host a service within IIS 5.1, 6.0 or within WAS, use the follows steps:</span></span>  
  
1.  <span data-ttu-id="cc18d-205">Скомпилируйте тип службы в сборку библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="cc18d-205">Compile the service type into a class library assembly.</span></span>  
  
2.  <span data-ttu-id="cc18d-206">Создайте файл службы с расширением SVC с директивой `@ ServiceHost` для идентификации типа службы:</span><span class="sxs-lookup"><span data-stu-id="cc18d-206">Create a service file with a .svc extension with an `@ ServiceHost` directive to identify the service type:</span></span>  
  
    ```  
    <%@ServiceHost language="c#" Service="MyService" %>  
    ```  
  
3.  <span data-ttu-id="cc18d-207">Скопируйте файл службы в виртуальный каталог, а сборку в подкаталог \bin этого виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="cc18d-207">Copy the service file into a virtual directory, and the assembly into the \bin subdirectory of that virtual directory.</span></span>  
  
4.  <span data-ttu-id="cc18d-208">Скопируйте файл конфигурации в виртуальный каталог и назовите его Web.config.</span><span class="sxs-lookup"><span data-stu-id="cc18d-208">Copy the configuration file into the virtual directory, and name it Web.config.</span></span>  
  
 <span data-ttu-id="cc18d-209">После этого приложение будет доступно по URL-адресу файла службы в корне приложения.</span><span class="sxs-lookup"><span data-stu-id="cc18d-209">The application is then accessible by using the URL of the service file in the application root.</span></span>  
  
 <span data-ttu-id="cc18d-210">Чтобы разместить службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в приложении .NET, скомпилируйте тип службы в сборку библиотеки классов, на которую ссылается приложение, и запрограммируйте приложение на размещение службы с помощью класса <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-210">To host a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service within a .NET application, compile the service type into a class library assembly referenced by the application, and program the application to host the service using the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="cc18d-211">Ниже приведен простой пример требуемого программирования:</span><span class="sxs-lookup"><span data-stu-id="cc18d-211">The following is an example of the basic programming required:</span></span>  
  
```  
string httpBaseAddress = "http://www.contoso.com:8000/";  
string tcpBaseAddress = "net.tcp://www.contoso.com:8080/";  
  
Uri httpBaseAddressUri = new Uri(httpBaseAddress);  
Uri tcpBaseAddressUri = new Uri(tcpBaseAddress);  
  
Uri[] baseAdresses = new Uri[] {   
 httpBaseAddressUri,  
 tcpBaseAddressUri};  
  
using(ServiceHost host = new ServiceHost(  
typeof(Service), //"Service" is the name of the service type baseAdresses))  
{  
     host.Open();  
  
     […] //Wait to receive messages  
     host.Close();  
}  
```  
  
 <span data-ttu-id="cc18d-212">В этом примере показано задание адресов для одного или нескольких транспортных протоколов при построении объекта <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-212">This example shows how addresses for one or more transport protocols are specified in the construction of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="cc18d-213">Эти адреса называются базовыми адресами.</span><span class="sxs-lookup"><span data-stu-id="cc18d-213">These addresses are referred to as base addresses.</span></span>  
  
 <span data-ttu-id="cc18d-214">Адрес, предоставляемый любой конечной точке службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], является адресом относительно базового адреса узла размещения конечной точки.</span><span class="sxs-lookup"><span data-stu-id="cc18d-214">The address provided for any endpoint of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is an address relative to a base address of the endpoint’s host.</span></span> <span data-ttu-id="cc18d-215">Узел размещения может иметь по одному базовому адресу для каждого транспортного протокола связи.</span><span class="sxs-lookup"><span data-stu-id="cc18d-215">The host can have one base address for each communication transport protocol.</span></span> <span data-ttu-id="cc18d-216">В приведенном выше примере файла конфигурации выбранная для конечной точки привязка <xref:System.ServiceModel.BasicHttpBinding> предполагает использование в качестве транспорта протокола HTTP, поэтому адрес конечной точки — `EchoService`— рассматривается относительно базового HTTP-адреса узла.</span><span class="sxs-lookup"><span data-stu-id="cc18d-216">In the sample configuration in the preceding configuration file, the <xref:System.ServiceModel.BasicHttpBinding> selected for the endpoint uses HTTP as the transport protocol, so the address of the endpoint, `EchoService`, is relative to the host’s HTTP base address.</span></span> <span data-ttu-id="cc18d-217">В случае узла из предыдущего примера базовый HTTP-адрес - http://www.contoso.com:8000/.</span><span class="sxs-lookup"><span data-stu-id="cc18d-217">In the case of the host in the preceding example, the HTTP base address is http://www.contoso.com:8000/.</span></span> <span data-ttu-id="cc18d-218">Для службы, размещенной в IIS или WAS, базовый адрес - это URL-адрес файла службы для этой службы.</span><span class="sxs-lookup"><span data-stu-id="cc18d-218">For a service hosted within IIS or WAS, the base address is the URL of the service’s service file.</span></span>  
  
 <span data-ttu-id="cc18d-219">Только службы, которые размещены в IIS или WAS и у которых транспортным протоколом является исключительно HTTP, могут работать в режиме совместимости [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc18d-219">Only services hosted in IIS or WAS, and which are configured with HTTP as the transport protocol exclusively, can be made to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET compatibility mode option.</span></span> <span data-ttu-id="cc18d-220">Для включения этого режима необходимо выполнить следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="cc18d-220">Turning that option on requires the following steps.</span></span>  
  
1.  <span data-ttu-id="cc18d-221">Программист должен добавить атрибут <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> в тип службы и указать, что режим совместимости с ASP.NET допускается либо требуется.</span><span class="sxs-lookup"><span data-stu-id="cc18d-221">The programmer must add the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> attribute to the service type and specify that ASP.NET compatibility mode is either allowed or required.</span></span>  
  
    ```  
    [System.ServiceModel.Activation.AspNetCompatibilityRequirements(  
          RequirementsMode=AspNetCompatbilityRequirementsMode.Require)]  
    public class DerivativesCalculatorServiceType: IDerivativesCalculator  
    ```  
  
2.  <span data-ttu-id="cc18d-222">Администратор должен настроить приложение на использование режима совместимости с ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc18d-222">The administrator must configure the application to use the ASP.NET compatibility mode.</span></span>  
  
    ```xml  
    <configuration>  
         <system.serviceModel>  
          <services>  
          […]  
          </services>  
          <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="cc18d-223">Приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также можно настраивать на использование для файлов служб расширения ASMX вместо SVC.</span><span class="sxs-lookup"><span data-stu-id="cc18d-223">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can also be configured to use .asmx as the extension for their service files rather than .svc.</span></span>  
  
    ```xml  
    <system.web>  
         <compilation>  
          <compilation debug="true">  
          <buildProviders>  
           <remove extension=".asmx"/>  
           <add extension=".asmx"   
            type="System.ServiceModel.ServiceBuildProvider,   
            Systemm.ServiceModel,   
            Version=3.0.0.0,   
            Culture=neutral,   
            PublicKeyToken=b77a5c561934e089" />  
          </buildProviders>  
          </compilation>  
         </compilation>  
    </system.web>  
    ```  
  
     <span data-ttu-id="cc18d-224">Эта возможность позволяет обойтись без внесения изменений в клиенты, настроенные на использование URL-адресов файлов служб с расширением ASMX, при переводе службы на использование [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc18d-224">That option can save you from having to modify clients that are configured to use the URLs of .asmx service files when modifying a service to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="client-development"></a><span data-ttu-id="cc18d-225">Разработка клиентов</span><span class="sxs-lookup"><span data-stu-id="cc18d-225">Client Development</span></span>  
 <span data-ttu-id="cc18d-226">Клиенты для веб-служб ASP.NET формируются с помощью программы командной строки WSDL.exe, которая предоставляет URL-адрес ASMX-файла в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="cc18d-226">Clients for ASP.NET Web services are generated using the command-line tool, WSDL.exe, which provides the URL of the .asmx file as input.</span></span> <span data-ttu-id="cc18d-227">Соответствующие средства, предоставляемые [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] — [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="cc18d-227">The corresponding tool provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="cc18d-228">Она формирует модуль кода с определением контракта службы и определением класса клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc18d-228">It generates a code module with the definition of the service contract and the definition of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class.</span></span> <span data-ttu-id="cc18d-229">Кроме того, она формирует файл конфигурации с адресом и привязкой службы.</span><span class="sxs-lookup"><span data-stu-id="cc18d-229">It also generates a configuration file with the address and binding of the service.</span></span>  
  
 <span data-ttu-id="cc18d-230">При программировании клиента удаленной службы обычно рекомендуется программировать в соответствии с асинхронной моделью.</span><span class="sxs-lookup"><span data-stu-id="cc18d-230">In programming a client of a remote service it is generally advisable to program according to an asynchronous pattern.</span></span> <span data-ttu-id="cc18d-231">Код, формируемый программой WSDL.exe, по умолчанию всегда предусматривает и синхронную, и асинхронную модели.</span><span class="sxs-lookup"><span data-stu-id="cc18d-231">The code generated by the WSDL.exe tool always provides for both a synchronous and an asynchronous pattern by default.</span></span> <span data-ttu-id="cc18d-232">Код, сгенерированный [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) можно предоставить либо шаблон.</span><span class="sxs-lookup"><span data-stu-id="cc18d-232">The code generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can provide for either pattern.</span></span> <span data-ttu-id="cc18d-233">По умолчанию предусматривается синхронная модель.</span><span class="sxs-lookup"><span data-stu-id="cc18d-233">It provides for the synchronous pattern by default.</span></span> <span data-ttu-id="cc18d-234">При выполнении программы с переключателем `/async` сформированный код предусматривает асинхронную модель.</span><span class="sxs-lookup"><span data-stu-id="cc18d-234">If the tool is executed with the `/async` switch, then the generated code provides for the asynchronous pattern.</span></span>  
  
 <span data-ttu-id="cc18d-235">Нет гарантии, что имена в классах клиентов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], сформированных программой WSDL.exe в ASP.NET, по умолчанию будут соответствовать именам в классах клиентов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], сформированных программой Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="cc18d-235">There is no guarantee that names in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client classes generated by ASP.NET’s WSDL.exe tool, by default, match the names in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client classes generated by the Svcutil.exe tool.</span></span> <span data-ttu-id="cc18d-236">В частности, имена свойств классов, которые должны сериализоваться с помощью сериализатора <xref:System.Xml.Serialization.XmlSerializer>, в формируемом программой Svcutil.exe коде по умолчанию получают суффикс "Property", который отсутствует в коде, формируемом WSDL.exe.</span><span class="sxs-lookup"><span data-stu-id="cc18d-236">In particular, the names of the properties of classes that have to be serialized using the <xref:System.Xml.Serialization.XmlSerializer> are, by default, given the suffix Property in the code generated by the Svcutil.exe tool, which is not the case with the WSDL.exe tool.</span></span>  
  
## <a name="message-representation"></a><span data-ttu-id="cc18d-237">Представление сообщений</span><span class="sxs-lookup"><span data-stu-id="cc18d-237">Message Representation</span></span>  
 <span data-ttu-id="cc18d-238">Заголовки сообщений SOAP, отправляемых и получаемых веб-службами ASP.NET, можно настроить.</span><span class="sxs-lookup"><span data-stu-id="cc18d-238">The headers of the SOAP messages sent and received by ASP.NET Web services can be customized.</span></span> <span data-ttu-id="cc18d-239">Из класса <xref:System.Web.Services.Protocols.SoapHeader> наследуется класс для определения структуры заголовка, после чего применяется атрибут <xref:System.Web.Services.Protocols.SoapHeaderAttribute>, чтобы указать на присутствие заголовка.</span><span class="sxs-lookup"><span data-stu-id="cc18d-239">A class is derived from <xref:System.Web.Services.Protocols.SoapHeader> to define the structure of the header, and then the <xref:System.Web.Services.Protocols.SoapHeaderAttribute> is used to indicate the presence of the header.</span></span>  
  
```  
public class SomeProtocol : SoapHeader  
{  
     public long CurrentValue;  
     public long Total;  
}  
  
[WebService]  
public interface IEcho  
{  
     SomeProtocol ProtocolHeader  
     {  
      get;  
     set;  
     }  
  
     [WebMethod]  
     [SoapHeader("ProtocolHeader")]  
     string PlaceOrders(PurchaseOrderType order);  
}  
  
public class Service: WebService, IEcho  
{  
     private SomeProtocol protocolHeader;  
  
     public SomeProtocol ProtocolHeader  
     {  
         get  
         {  
              return this.protocolHeader;  
         }  
  
         set  
         {  
              this.protocolHeader = value;  
         }  
     }  
  
     string PlaceOrders(PurchaseOrderType order)  
     {  
         long currentValue = this.protocolHeader.CurrentValue;  
     }  
}  
```  
  
 <span data-ttu-id="cc18d-240">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предусмотрены атрибуты - <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute> и <xref:System.ServiceModel.MessageBodyMemberAttribute> - для описания структуры сообщений SOAP, отправляемых и получаемых службой.</span><span class="sxs-lookup"><span data-stu-id="cc18d-240">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides the attributes, <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>, and <xref:System.ServiceModel.MessageBodyMemberAttribute> to describe the structure of the SOAP messages sent and received by a service.</span></span>  
  
```  
[DataContract]  
public class SomeProtocol  
{  
     [DataMember]  
     public long CurrentValue;  
     [DataMember]  
     public long Total;  
}  
  
[DataContract]  
public class Item  
{  
     [DataMember]  
     public string ItemNumber;  
     [DataMember]  
     public decimal Quantity;  
     [DataMember]  
     public decimal UnitPrice;  
}  
  
[MessageContract]  
public class ItemMesage  
{  
     [MessageHeader]  
     public SomeProtocol ProtocolHeader;  
     [MessageBody]  
     public Item Content;  
}  
  
[ServiceContract]  
public interface IItemService  
{  
     [OperationContract]  
     public void DeliverItem(ItemMessage itemMessage);  
}  
```  
  
 <span data-ttu-id="cc18d-241">Этот синтаксис дает явное представление структуры сообщений, тогда как в веб-службе ASP.NET структура сообщений подразумевается в коде.</span><span class="sxs-lookup"><span data-stu-id="cc18d-241">This syntax yields an explicit representation of the structure of the messages, whereas the structure of messages is implied by the code of an ASP.NET Web service.</span></span> <span data-ttu-id="cc18d-242">Кроме того, в синтаксисе ASP.NET заголовки сообщений представляются как свойства службы, таких как свойство `ProtocolHeader` в предыдущем примере, тогда как в синтаксисе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] они представляются более точно - как свойства сообщений.</span><span class="sxs-lookup"><span data-stu-id="cc18d-242">Also, in the ASP.NET syntax, message headers are represented as properties of the service, such as the `ProtocolHeader` property in the previous example, whereas in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] syntax, they are more accurately represented as properties of messages.</span></span> <span data-ttu-id="cc18d-243">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также позволяет добавлять заголовки сообщений в конфигурацию конечных точек.</span><span class="sxs-lookup"><span data-stu-id="cc18d-243">Also, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows message headers to be added to the configuration of endpoints.</span></span>  
  
```xml  
<service name="Service ">  
     <endpoint   
      address="EchoService"  
      binding="basicHttpBinding"  
      contract="IEchoService ">  
      <headers>  
      <dsig:X509Certificate   
       xmlns:dsig="http://www.w3.org/2000/09/xmldsig#">  
       ...  
      </dsig:X509Certificate>  
      </headers>  
     </endpoint>  
</service>  
```  
  
 <span data-ttu-id="cc18d-244">Это позволяет обойтись без ссылок на заголовки инфраструктурных протоколов в коде клиента или службы: заголовки добавляются в сообщения в соответствии с тем, как настроена конечная точка.</span><span class="sxs-lookup"><span data-stu-id="cc18d-244">That option allows you to avoid any reference to infrastructural protocol headers in the code for a client or service: the headers are added to messages because of how the endpoint is configured.</span></span>  
  
## <a name="service-description"></a><span data-ttu-id="cc18d-245">Описание службы</span><span class="sxs-lookup"><span data-stu-id="cc18d-245">Service Description</span></span>  
 <span data-ttu-id="cc18d-246">При выдаче запроса HTTP-GET на ASMX-файл веб-службы ASP.NET с запросом "WSDL" ASP.NET формирует WSDL-код для описания службы.</span><span class="sxs-lookup"><span data-stu-id="cc18d-246">Issuing an HTTP GET request for the .asmx file of an ASP.NET Web service with the query WSDL causes ASP.NET to generate WSDL to describe the service.</span></span> <span data-ttu-id="cc18d-247">Этот WSDL-код возвращается в качестве ответа на запрос HTTP-GET.</span><span class="sxs-lookup"><span data-stu-id="cc18d-247">It returns that WSDL as the response to the request.</span></span>  
  
 <span data-ttu-id="cc18d-248">В ASP.NET 2.0 появилась возможность проверять, совместима ли служба со спецификацией Basic Profile 1.1 Организации по обеспечению взаимодействия веб-служб (Web Services-Interoperability Organization, WS-I), и вставлять утверждение о совместимости службы в WSDL.</span><span class="sxs-lookup"><span data-stu-id="cc18d-248">ASP.NET 2.0 made it possible to validate that a service is compliant with the Basic Profile 1.1 of the Web Services-Interoperability Organization (WS-I), and to insert a claim that the service is compliant into its WSDL.</span></span> <span data-ttu-id="cc18d-249">Это делается с помощью параметров `ConformsTo` и `EmitConformanceClaims` атрибута <xref:System.Web.Services.WebServiceBindingAttribute>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-249">That is done using the `ConformsTo` and `EmitConformanceClaims` parameters of the <xref:System.Web.Services.WebServiceBindingAttribute> attribute.</span></span>  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 <span data-ttu-id="cc18d-250">WSDL-код, формируемый ASP.NET для службы, можно настраивать.</span><span class="sxs-lookup"><span data-stu-id="cc18d-250">The WSDL that ASP.NET generates for a service can be customized.</span></span> <span data-ttu-id="cc18d-251">Настройка производится путем создания класса, производного от <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension>, для добавления элементов в WSDL-код.</span><span class="sxs-lookup"><span data-stu-id="cc18d-251">Customizations are made by creating a derived class of <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension> to add items to the WSDL.</span></span>  
  
 <span data-ttu-id="cc18d-252">При выдаче запроса HTTP-GET с запросом "WSDL" на SVC-файл службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с конечной точкой HTTP, размещенной в IIS 51, 6.0 или WAS, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] возвращает в ответ WSDL-код, описывающий службу.</span><span class="sxs-lookup"><span data-stu-id="cc18d-252">Issuing an HTTP GET request with the query WSDL for the .svc file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with an HTTP endpoint hosted within IIS 51, 6.0 or WAS causes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to respond with WSDL to describe the service.</span></span> <span data-ttu-id="cc18d-253">Передача запроса HTTP-GET с запросом «WSDL» на базовый HTTP-адрес службы, размещенной в приложении .NET, имеет тот же эффект, если параметр httpGetEnabled имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="cc18d-253">Issuing an HTTP GET request with the query WSDL to the HTTP base address of a service hosted within a .NET application has the same effect if httpGetEnabled is set to true.</span></span>  
  
 <span data-ttu-id="cc18d-254">В то же время [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также возвращает WSDL-код, сформированный для описания службы, в ответ на запросы WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="cc18d-254">However, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] also responds to WS-MetadataExchange requests with WSDL that it generates to describe a service.</span></span> <span data-ttu-id="cc18d-255">Веб-службы ASP.NET не располагают встроенной поддержкой запросов WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="cc18d-255">ASP.NET Web services do not have built-in support for WS-MetadataExchange requests.</span></span>  
  
 <span data-ttu-id="cc18d-256">WSDL-код, формируемый [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], очень гибко настраивается.</span><span class="sxs-lookup"><span data-stu-id="cc18d-256">The WSDL that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates can be extensively customized.</span></span> <span data-ttu-id="cc18d-257">Класс <xref:System.ServiceModel.Description.ServiceMetadataBehavior> предоставляет некоторые средства для настройки WSDL-кода.</span><span class="sxs-lookup"><span data-stu-id="cc18d-257">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class provides some facilities for customizing the WSDL.</span></span> <span data-ttu-id="cc18d-258">Вместо формирования WSDL-кода [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также можно настроить на использование статического WSDL-файла, находящегося по заданному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="cc18d-258">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can also be configured to not generate WSDL, but rather to use a static WSDL file at a given URL.</span></span>  
  
```xml  
<behaviors>  
     <behavior name="DescriptionBehavior">  
     <metadataPublishing   
      enableMetadataExchange="true"   
      enableGetWsdl="true"   
      enableHelpPage="true"   
      metadataLocation=  
      "http://localhost/DerivativesCalculatorService/Service.WSDL"/>  
     </behavior>  
</behaviors>  
```  
  
## <a name="exception-handling"></a><span data-ttu-id="cc18d-259">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="cc18d-259">Exception Handling</span></span>  
 <span data-ttu-id="cc18d-260">В веб-службах ASP.NET необработанные исключения возвращаются клиентам в виде ошибок SOAP.</span><span class="sxs-lookup"><span data-stu-id="cc18d-260">In ASP.NET Web services, unhandled exceptions are returned to clients as SOAP faults.</span></span> <span data-ttu-id="cc18d-261">Также можно явно вызывать исключения класса <xref:System.Web.Services.Protocols.SoapException>, что позволяет в большей степени контролировать содержимое ошибки SOAP, передаваемое клиенту.</span><span class="sxs-lookup"><span data-stu-id="cc18d-261">You can also explicitly throw instances of the <xref:System.Web.Services.Protocols.SoapException> class and have more control over the content of the SOAP fault that gets transmitted to the client.</span></span>  
  
 <span data-ttu-id="cc18d-262">В службах [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] необработанные исключения не возвращаются клиентам в виде ошибок SOAP во избежание случайного раскрытия конфиденциальной информации через исключения.</span><span class="sxs-lookup"><span data-stu-id="cc18d-262">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services, unhandled exceptions are not returned to clients as SOAP faults to prevent sensitive information being inadvertently exposed through the exceptions.</span></span> <span data-ttu-id="cc18d-263">Предусмотрен параметр конфигурации для возвращения необработанных исключений клиентам в целях отладки.</span><span class="sxs-lookup"><span data-stu-id="cc18d-263">A configuration setting is provided to have unhandled exceptions returned to clients for the purpose of debugging.</span></span>  
  
 <span data-ttu-id="cc18d-264">Для возвращения ошибок SOAP клиентам можно вызывать исключения универсального типа - <xref:System.ServiceModel.FaultException%601> - используя в качестве универсального типа тип контракта данных.</span><span class="sxs-lookup"><span data-stu-id="cc18d-264">To return SOAP faults to clients, you can throw instances of the generic type, <xref:System.ServiceModel.FaultException%601>, using the data contract type as the generic type.</span></span> <span data-ttu-id="cc18d-265">Также можно добавлять в операции атрибуты <xref:System.ServiceModel.FaultContractAttribute> для указания того, какие ошибки могут быть выданы операцией.</span><span class="sxs-lookup"><span data-stu-id="cc18d-265">You can also add <xref:System.ServiceModel.FaultContractAttribute> attributes to operations to specify the faults that an operation might yield.</span></span>  
  
```  
[DataContract]  
public class MathFault  
{   
     [DataMember]  
     public string operation;  
     [DataMember]  
     public string problemType;  
}  
  
[ServiceContract]  
public interface ICalculator  
{  
     [OperationContract]  
     [FaultContract(typeof(MathFault))]  
     int Divide(int n1, int n2);  
}  
```  
  
 <span data-ttu-id="cc18d-266">В этом случае возможные ошибки объявляются в WSDL-коде для службы, что дает разработчикам клиентов возможность предвидеть, какие ошибки могут произойти в результате операции, и написать соответствующие инструкции catch.</span><span class="sxs-lookup"><span data-stu-id="cc18d-266">Doing so results in the possible faults being advertised in the WSDL for the service, allowing client programmers to anticipate which faults can result from an operation, and write the appropriate catch statements.</span></span>  
  
```  
try  
{  
     result = client.Divide(value1, value2);  
}  
catch (FaultException<MathFault> e)  
{  
 Console.WriteLine("FaultException<MathFault>: Math fault while doing "  
  + e.Detail.operation   
  + ". Problem: "   
  + e.Detail.problemType);  
}  
```  
  
## <a name="state-management"></a><span data-ttu-id="cc18d-267">Управление состоянием</span><span class="sxs-lookup"><span data-stu-id="cc18d-267">State Management</span></span>  
 <span data-ttu-id="cc18d-268">Класс, используемый для реализации веб-службы ASP.NET, может наследоваться от класса <xref:System.Web.Services.WebService>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-268">The class used to implement an ASP.NET Web service may be derived from <xref:System.Web.Services.WebService>.</span></span>  
  
```  
public class Service : WebService, IEcho  
{  
  
 public string Echo(string input)  
 {  
  return input;  
 }  
}  
```  
  
 <span data-ttu-id="cc18d-269">В этом случае класс можно запрограммировать на использование свойства Context базового класса <xref:System.Web.Services.WebService> для доступа к объекту <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-269">In that case, the class can be programmed to use the <xref:System.Web.Services.WebService> base class’ Context property to access a <xref:System.Web.HttpContext> object.</span></span> <span data-ttu-id="cc18d-270">Объект <xref:System.Web.HttpContext> можно использовать для обновления и извлечения информации о состоянии приложения (с помощью его свойства Application) и для обновления и извлечения информации о состоянии сеанса (с помощью его свойства Session).</span><span class="sxs-lookup"><span data-stu-id="cc18d-270">The <xref:System.Web.HttpContext> object can be used to update and retrieve application state information by using its Application property, and can be used to update and retrieve session state information by using its Session property.</span></span>  
  
 <span data-ttu-id="cc18d-271">ASP.NET позволяет в значительной степени контролировать место фактического хранения информации о состоянии сеанса, для доступа к которой используется свойство Session объекта <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-271">ASP.NET provides considerable control over where the session state information accessed by using the Session property of the <xref:System.Web.HttpContext> is actually stored.</span></span> <span data-ttu-id="cc18d-272">Эта информация может храниться в файлах cookie, в базе данных, в памяти текущего сервера или в памяти указанного сервера.</span><span class="sxs-lookup"><span data-stu-id="cc18d-272">It may be stored in cookies, in a database, in the memory of the current server, or in the memory of a designated server.</span></span> <span data-ttu-id="cc18d-273">Место хранения информации указывается в файле конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="cc18d-273">The choice is made in the service’s configuration file.</span></span>  
  
 <span data-ttu-id="cc18d-274">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предоставляет расширяемые объекты для управления состоянием.</span><span class="sxs-lookup"><span data-stu-id="cc18d-274">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides extensible objects for state management.</span></span> <span data-ttu-id="cc18d-275">Расширяемые объекты - это объекты, реализующие интерфейс <xref:System.ServiceModel.IExtensibleObject%601>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-275">Extensible objects are objects that implement <xref:System.ServiceModel.IExtensibleObject%601>.</span></span> <span data-ttu-id="cc18d-276">Наиболее важными из расширяемых объектов являются <xref:System.ServiceModel.ServiceHostBase> и <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-276">The most important extensible objects are <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="cc18d-277">`ServiceHostBase` позволяет сохранять состояние, к которому могут обращаться все экземпляры всех типов служб на одном и том же узле, тогда как `InstanceContext` позволяет сохранять состояние, к которому может обращаться любой код, выполняемый в одном экземпляре типа службы.</span><span class="sxs-lookup"><span data-stu-id="cc18d-277">`ServiceHostBase` allows you to maintain state that all of the instances of all of the service types on the same host can access, while `InstanceContext` allows you to maintain state that can be accessed by any code running within the same instance of a service type.</span></span>  
  
 <span data-ttu-id="cc18d-278">В этом примере тип службы, `TradingSystem`, имеет атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute>, который указывает, что все вызовы от одного и того же экземпляра клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] должны направляться одному и тому же экземпляру типа службы.</span><span class="sxs-lookup"><span data-stu-id="cc18d-278">Here, the service type, `TradingSystem`, has a <xref:System.ServiceModel.ServiceBehaviorAttribute> that specifies that all calls from the same [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client instance are routed to the same instance of the service type.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
public class TradingSystem: ITradingService  
```  
  
 <span data-ttu-id="cc18d-279">Класс, `DealData`, определяет состояние, к которому может обращаться любой код, выполняемый в одном и том же экземпляре типа службы.</span><span class="sxs-lookup"><span data-stu-id="cc18d-279">The class, `DealData`, defines state that can be accessed by any code running in the same instance of a service type.</span></span>  
  
```  
internal class DealData: IExtension<InstanceContext>  
{  
 public string DealIdentifier = null;  
 public Trade[] Trades = null;  
}  
```  
  
 <span data-ttu-id="cc18d-280">В коде типа службы, реализующем одну из операций контракта службы, к состоянию текущего экземпляра типа службы добавляется объект состояния `DealData`.</span><span class="sxs-lookup"><span data-stu-id="cc18d-280">In the code of the service type that implements one of the operations of the service contract, a `DealData` state object is added to the state of the current instance of the service type.</span></span>  
  
```  
string ITradingService.BeginDeal()  
{  
 string dealIdentifier = Guid.NewGuid().ToString();  
 DealData state = new DealData(dealIdentifier);  
 OperationContext.Current.InstanceContext.Extensions.Add(state);  
 return dealIdentifier;  
}  
```  
  
 <span data-ttu-id="cc18d-281">Этот объект состояния затем может быть извлечен и изменен кодом, реализующим другую операцию контракта службы.</span><span class="sxs-lookup"><span data-stu-id="cc18d-281">That state object can then be retrieved and modified by the code that implements another of the service contract’s operations.</span></span>  
  
```  
void ITradingService.AddTrade(Trade trade)  
{  
 DealData dealData =  OperationContext.Current.InstanceContext.Extensions.Find<DealData>();  
 dealData.AddTrade(trade);  
}  
```  
  
 <span data-ttu-id="cc18d-282">Тогда как ASP.NET позволяет контролировать место фактического хранения информации о состоянии в классе <xref:System.Web.HttpContext>, в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], по крайней мере в первоначальной версии, не предусмотрена возможность управления местом хранения расширяемых объектов.</span><span class="sxs-lookup"><span data-stu-id="cc18d-282">Whereas ASP.NET provides control over where state information in the <xref:System.Web.HttpContext> class is actually stored, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], at least in its initial version, provides no control over where extensible objects are stored.</span></span> <span data-ttu-id="cc18d-283">Это представляет собой наиболее важную причину использовать режим совместимости с ASP.NET для службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc18d-283">That constitutes the very best reason for selecting the ASP.NET compatibility mode for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="cc18d-284">Если настраиваемое управление состоянием является обязательным условием, выбор режима совместимости с ASP.NET позволяет использовать средства класса <xref:System.Web.HttpContext> в точности так, как они используются в ASP.NET, а также настраивать место хранения информации о состоянии с помощью класса <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-284">If configurable state management is imperative, then opting for the ASP.NET compatibility mode allows you to use the facilities of the <xref:System.Web.HttpContext> class exactly as they are used in ASP.NET, and also to configure where state information managed by using the <xref:System.Web.HttpContext> class is stored.</span></span>  
  
## <a name="security"></a><span data-ttu-id="cc18d-285">Безопасность</span><span class="sxs-lookup"><span data-stu-id="cc18d-285">Security</span></span>  
 <span data-ttu-id="cc18d-286">Для защиты веб-служб ASP.NET используются те же механизмы, что и для защиты любого приложения IIS.</span><span class="sxs-lookup"><span data-stu-id="cc18d-286">The options for securing ASP.NET Web services are those for securing any IIS application.</span></span> <span data-ttu-id="cc18d-287">Поскольку приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] могут размещаться не только в службах IIS, но также в любом исполняемом файле .NET, механизмы защиты приложений [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] должны быть независимы от средств IIS.</span><span class="sxs-lookup"><span data-stu-id="cc18d-287">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can be hosted not only within IIS but also within any .NET executable, the options for securing [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications must be made independent from the facilities of IIS.</span></span> <span data-ttu-id="cc18d-288">Тем не менее, средства, предоставляемые веб-службам ASP.NET, также доступны для служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], выполняющихся в режиме совместимости с ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc18d-288">However, the facilities provided for ASP.NET Web services are also available for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services running in ASP.NET compatibility mode.</span></span>  
  
### <a name="security-authentication"></a><span data-ttu-id="cc18d-289">Безопасность: проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="cc18d-289">Security: Authentication</span></span>  
 <span data-ttu-id="cc18d-290">Службы IIS предоставляют средства для управления доступом к приложениям, позволяющие выбрать либо анонимный доступ, либо один из ряда режимов проверки подлинности: проверка подлинности Windows, дайджест-проверка подлинности, обычная проверка подлинности и проверка подлинности по паспорту .NET Passport.</span><span class="sxs-lookup"><span data-stu-id="cc18d-290">IIS provides facilities for controlling access to applications by which you can select either anonymous access or a variety of modes of authentication: Windows Authentication, Digest Authentication, Basic Authentication, and .NET Passport Authentication.</span></span> <span data-ttu-id="cc18d-291">Вариант с проверкой подлинности Windows можно использовать для управления доступом к веб-службам ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc18d-291">The Windows Authentication option can be used to control access to ASP.NET Web services.</span></span> <span data-ttu-id="cc18d-292">Однако при размещении приложений [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в службах IIS последние необходимо настроить на разрешение анонимного доступа к приложению, чтобы проверкой подлинности могла управлять сама система [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], которая поддерживает, в числе прочих вариантов, проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="cc18d-292">However, when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications are hosted within IIS, IIS must be configured to permit anonymous access to the application, so that authentication can be managed by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] itself, which does support Windows authentication among various other options.</span></span> <span data-ttu-id="cc18d-293">Другие встроенные средства включают маркеры имени пользователя, сертификаты X.509, маркеры SAML и карту CardSpace; также можно определять пользовательские механизмы проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="cc18d-293">The other options that are built-in include username tokens, X.509 certificates, SAML tokens, and CardSpace card, but custom authentication mechanisms can also be defined.</span></span>  
  
### <a name="security-impersonation"></a><span data-ttu-id="cc18d-294">Безопасность: олицетворение</span><span class="sxs-lookup"><span data-stu-id="cc18d-294">Security: Impersonation</span></span>  
 <span data-ttu-id="cc18d-295">ASP.NET предоставляет элемент удостоверения, посредством которого веб-служба ASP.NET может олицетворять определенного пользователя или любого пользователя, учетные данные которого переданы в текущем запросе.</span><span class="sxs-lookup"><span data-stu-id="cc18d-295">ASP.NET provides an identity element by which an ASP.NET Web service can be made to impersonate a particular user or whichever user’s credentials are provided with the current request.</span></span> <span data-ttu-id="cc18d-296">Этот элемент можно использовать для настройки олицетворения в приложениях [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], выполняющихся в режиме совместимости с ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc18d-296">That element can be used to configure impersonation in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications running in ASP.NET compatibility mode.</span></span>  
  
 <span data-ttu-id="cc18d-297">Система конфигурации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предусматривает собственный элемент удостоверения для задания определенного пользователя, которого требуется олицетворять.</span><span class="sxs-lookup"><span data-stu-id="cc18d-297">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration system provides its own identity element for designating a particular user to impersonate.</span></span> <span data-ttu-id="cc18d-298">Кроме того, клиенты и службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно отдельно настраивать на олицетворение.</span><span class="sxs-lookup"><span data-stu-id="cc18d-298">Also, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients and services can be independently configured for impersonation.</span></span> <span data-ttu-id="cc18d-299">Клиенты можно настроить на олицетворение текущего пользователя при передаче запросов.</span><span class="sxs-lookup"><span data-stu-id="cc18d-299">Clients can be configured to impersonate the current user when they transmit requests.</span></span>  
  
```xml  
<behaviors>  
     <behavior name="DerivativesCalculatorClientBehavior">  
      <clientCredentials>  
      <windows allowedImpersonationLevel="Impersonation"/>  
      </clientCredentials>  
     </behavior>  
</behaviors>  
```  
  
 <span data-ttu-id="cc18d-300">Операции службы можно настроить на олицетворение любого пользователя, учетные данные которого переданы в текущем запросе.</span><span class="sxs-lookup"><span data-stu-id="cc18d-300">Service operations can be configured to impersonate whichever user’s credentials are provided with the current request.</span></span>  
  
```  
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public void Receive(Message input)  
```  
  
### <a name="security-authorization-using-access-control-lists"></a><span data-ttu-id="cc18d-301">Безопасность: авторизация с использованием списков управления доступом</span><span class="sxs-lookup"><span data-stu-id="cc18d-301">Security: Authorization using Access Control Lists</span></span>  
 <span data-ttu-id="cc18d-302">Для ограничения доступа к ASMX-файлам можно использовать списки управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="cc18d-302">Access Control Lists (ACLs) can be used to restrict access to .asmx files.</span></span> <span data-ttu-id="cc18d-303">Однако применительно к SVC-файлам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] списки ACL игнорируются, если служба не работает в режиме совместимости с ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc18d-303">However, ACLs on [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .svc files are ignored except in ASP.NET compatibility mode.</span></span>  
  
### <a name="security-role-based-authorization"></a><span data-ttu-id="cc18d-304">Безопасность: авторизация на основе ролей</span><span class="sxs-lookup"><span data-stu-id="cc18d-304">Security: Role-based Authorization</span></span>  
 <span data-ttu-id="cc18d-305">Режим проверки подлинности Windows, предоставляемый службами IIS, можно использовать в сочетании с предусмотренным в языке конфигурации ASP.NET элементом авторизации для упрощения авторизации на основе ролей для веб-служб ASP.NET, основанных на группах Windows, которым назначены пользователи.</span><span class="sxs-lookup"><span data-stu-id="cc18d-305">The IIS Windows Authentication option can be used in conjunction with the authorization element provided by the ASP.NET configuration language to facilitate role-based authorization for ASP.NET Web services based on the Windows groups to which users are assigned.</span></span> <span data-ttu-id="cc18d-306">В ASP.NET 2.0 появился более общий механизм авторизации на основе ролей: поставщики ролей.</span><span class="sxs-lookup"><span data-stu-id="cc18d-306">ASP.NET 2.0 introduced a more general role-based authorization mechanism: role providers.</span></span>  
  
 <span data-ttu-id="cc18d-307">Поставщики ролей - это классы, реализующие базовый интерфейс для отправки запросов о ролях, которым назначен пользователь, причем каждый поставщик ролей предназначен для извлечения этой информации из определенного источника.</span><span class="sxs-lookup"><span data-stu-id="cc18d-307">Role providers are classes that all implement a basic interface for enquiring about the roles to which a user is assigned, but each role provider knows how to retrieve that information from a different source.</span></span> <span data-ttu-id="cc18d-308">ASP.NET 2.0 предоставляет поставщик ролей, который может извлекать назначения ролей из базы данных Microsoft SQL Server, и еще один поставщик, способный извлекать назначения ролей из диспетчера авторизации Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="cc18d-308">ASP.NET 2.0 provides a role provider that can retrieve role assignments from a Microsoft SQL Server database, and another that can retrieve role assignments from the Windows Server 2003 Authorization Manager.</span></span>  
  
 <span data-ttu-id="cc18d-309">Механизм поставщиков ролей на самом деле можно использовать независимо от ASP.NET в любом приложении .NET, в том числе приложении [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc18d-309">The role provider mechanism can actually be used independently of ASP.NET in any .NET application, including a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="cc18d-310">В приведенном ниже образце конфигурации для приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] показано, как с помощью поведения <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> выбирается использование поставщика ролей ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc18d-310">The following sample configuration for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application shows how the use of an ASP.NET role provider is an option selected by means of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span></span>  
  
```xml  
<system.serviceModel>  
     <services>  
         <service name="Service.ResourceAccessServiceType"   
             behaviorConfiguration="ServiceBehavior">  
             <endpoint   
              address="ResourceAccessService"   
              binding="wsHttpBinding"   
              contract="Service.IResourceAccessContract"/>  
         </service>  
     </services>  
     <behaviors>  
       <behavior name="ServiceBehavior">  
       <serviceAuthorization principalPermissionMode="UseAspNetRoles"/>  
      </behavior>  
     </behaviors>  
</system.serviceModel>  
```  
  
### <a name="security-claims-based-authorization"></a><span data-ttu-id="cc18d-311">Безопасность: авторизация на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="cc18d-311">Security: Claims-based Authorization</span></span>  
 <span data-ttu-id="cc18d-312">Одним из важнейших нововведений, появившихся в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], является хорошо проработанная поддержка авторизации доступа к защищенным ресурсам на основе утверждений.</span><span class="sxs-lookup"><span data-stu-id="cc18d-312">One of the most important innovations of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is its thorough support for authorizing access to protected resources based on claims.</span></span> <span data-ttu-id="cc18d-313">Утверждения состоят из типа, права и значения. В качестве примера можно привести водительское удостоверение:</span><span class="sxs-lookup"><span data-stu-id="cc18d-313">Claims consist of a type, a right and a value, a drivers’ license, for example.</span></span> <span data-ttu-id="cc18d-314">оно содержит ряд утверждений о своем предъявителе, одним из которых является дата рождения предъявителя.</span><span class="sxs-lookup"><span data-stu-id="cc18d-314">It makes a set of claims about the bearer, one of which is the bearer’s date of birth.</span></span> <span data-ttu-id="cc18d-315">Тип этого утверждения - дата рождения, а значение утверждения - дата рождения водителя.</span><span class="sxs-lookup"><span data-stu-id="cc18d-315">The type of that claim is date of birth, while the value of the claim is the driver’s birth date.</span></span> <span data-ttu-id="cc18d-316">Право, которое утверждение дает предъявителю, указывает, что предъявитель может делать со значением утверждения.</span><span class="sxs-lookup"><span data-stu-id="cc18d-316">The right that a claim confers on the bearer specifies what the bearer can do with the claim’s value.</span></span> <span data-ttu-id="cc18d-317">В случае утверждения даты рождения водителя право состоит во владении: эта дата рождения принадлежит водителю, однако он не может, например, изменять ее.</span><span class="sxs-lookup"><span data-stu-id="cc18d-317">In the case of the claim of the driver’s date of birth, the right is possession: the driver possesses that date of birth but cannot, for example, alter it.</span></span> <span data-ttu-id="cc18d-318">Авторизация на основе утверждений включает в себя авторизацию на основе ролей, поскольку роли являются одним из типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="cc18d-318">Claims-based authorization encloses role-based authorization, because roles are a type of claim.</span></span>  
  
 <span data-ttu-id="cc18d-319">Авторизация на основе утверждений осуществляется путем сравнения набора утверждений с требованиями доступа к операции и предоставления доступа к операции или отказа в доступе к операции в зависимости от результатов этого сравнения.</span><span class="sxs-lookup"><span data-stu-id="cc18d-319">Authorization based on claims is accomplished by comparing a set of claims to the access requirements of the operation and, depending on the outcome of that comparison, granting or denying access to the operation.</span></span> <span data-ttu-id="cc18d-320">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно задать класс, который будет использоваться для выполнения авторизации на основе утверждений, снова-таки путем присвоения значения свойству `ServiceAuthorizationManager` поведения <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span><span class="sxs-lookup"><span data-stu-id="cc18d-320">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], you can specify a class to use to run claims-based authorization, once again by assigning a value to the `ServiceAuthorizationManager` property of <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span></span>  
  
```xml  
<behaviors>  
     <behavior name='ServiceBehavior'>  
     <serviceAuthorization   
     serviceAuthorizationManagerType=  
                   'Service.AccessChecker, Service' />  
     </behavior>  
</behaviors>  
```  
  
 <span data-ttu-id="cc18d-321">Классы, используемые для выполнения авторизации на основе утверждений, должны быть производными от класса <xref:System.ServiceModel.ServiceAuthorizationManager>, в котором имеется только один метод для переопределения - `AccessCheck()`.</span><span class="sxs-lookup"><span data-stu-id="cc18d-321">Classes used to run claims-based authorization must derive from <xref:System.ServiceModel.ServiceAuthorizationManager>, which has just one method to override, `AccessCheck()`.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc18d-322"> вызывает этот метод при каждом вызове операции службы, передавая объект <xref:System.ServiceModel.OperationContext>, который содержит утверждения пользователя в свойстве `ServiceSecurityContext.AuthorizationContext`.</span><span class="sxs-lookup"><span data-stu-id="cc18d-322"> calls that method whenever an operation of the service is invoked and provides a <xref:System.ServiceModel.OperationContext> object, which has the claims for the user in its `ServiceSecurityContext.AuthorizationContext` property.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc18d-323"> выполняет действие, собирая утверждения о пользователе из всего массива данных, представленных пользователем для проверки подлинности, после чего остается только оценить, достаточно ли этих утверждений для выполнения запрошенной операции.</span><span class="sxs-lookup"><span data-stu-id="cc18d-323"> does the work of assembling claims about the user from whatever security token the user provided for authentication, which leaves the of task of evaluating whether those claims suffice for the operation in question.</span></span>  
  
 <span data-ttu-id="cc18d-324">Автоматический сбор системой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] утверждений из любого типа маркера безопасности - очень значительное нововведение, поскольку это делает код для авторизации на основе утверждений полностью независимым от механизма проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="cc18d-324">That [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatically assembles claims from any kind of security token is a highly significant innovation, because it makes the code for authorization based on the claims entirely independent of the authentication mechanism.</span></span> <span data-ttu-id="cc18d-325">В противоположность этому авторизация с использованием списков ACL или ролей в ASP.NET тесно связана с проверкой подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="cc18d-325">By contrast, authorization using ACLs or roles in ASP.NET is closely tied to Windows authentication.</span></span>  
  
### <a name="security-confidentiality"></a><span data-ttu-id="cc18d-326">Безопасность: конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="cc18d-326">Security: Confidentiality</span></span>  
 <span data-ttu-id="cc18d-327">Конфиденциальность сообщений, отправляемых и принимаемых веб-службами ASP.NET, может быть обеспечена на уровне транспорта путем настройки приложения в IIS на использование протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cc18d-327">The confidentiality of messages exchanged with ASP.NET Web services can be ensured at the transport level by configuring the application within IIS to use the Secure Hypertext Transfer Protocol (HTTPS).</span></span> <span data-ttu-id="cc18d-328">Это возможно и для приложений [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещаемых в IIS.</span><span class="sxs-lookup"><span data-stu-id="cc18d-328">The same can be done for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications hosted within IIS.</span></span> <span data-ttu-id="cc18d-329">В то же время приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещаемые не в IIS, также можно настроить на использование защищенного транспортного протокола.</span><span class="sxs-lookup"><span data-stu-id="cc18d-329">However, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications hosted outside of IIS can also be configured to use a secure transport protocol.</span></span> <span data-ttu-id="cc18d-330">Что более важно, приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также можно настраивать на защиту сообщений перед их транспортировкой с использованием протокола WS-Security.</span><span class="sxs-lookup"><span data-stu-id="cc18d-330">More important, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can also be configured to secure the messages before they are transported, using the WS-Security protocol.</span></span> <span data-ttu-id="cc18d-331">Защита только тела сообщения с использованием WS-Security позволяет передавать его с соблюдением конфиденциальности в пункт назначения через посредников.</span><span class="sxs-lookup"><span data-stu-id="cc18d-331">Securing just the body of a message using WS-Security allows it to be transmitted confidentially across intermediaries before reaching its final destination.</span></span>  
  
## <a name="globalization"></a><span data-ttu-id="cc18d-332">Глобализация</span><span class="sxs-lookup"><span data-stu-id="cc18d-332">Globalization</span></span>  
 <span data-ttu-id="cc18d-333">Язык конфигурации ASP.NET позволяет задавать язык и региональные параметры для отдельных служб.</span><span class="sxs-lookup"><span data-stu-id="cc18d-333">The ASP.NET configuration language allows you to specify the culture for individual services.</span></span> <span data-ttu-id="cc18d-334">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживает этот параметр конфигурации, за исключением работы в режиме совместимости с ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc18d-334">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not support that configuration setting except in ASP.NET compatibility mode.</span></span> <span data-ttu-id="cc18d-335">Для локализации службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], работающей не в режиме совместимости с ASP.NET необходимо скомпилировать тип службы в сборки для конкретных языков и региональных параметров и предусмотреть для каждой такой сборки отдельную конечную точку с данным языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="cc18d-335">To localize a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that does not use ASP.NET compatibility mode, compile the service type into culture-specific assemblies, and have separate culture-specific endpoints for each culture-specific assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc18d-336">См. также</span><span class="sxs-lookup"><span data-stu-id="cc18d-336">See Also</span></span>  
 [<span data-ttu-id="cc18d-337">Сравнение веб-служб ASP.NET на основе WCF по назначению и используемым стандартам</span><span class="sxs-lookup"><span data-stu-id="cc18d-337">Comparing ASP.NET Web Services to WCF Based on Purpose and Standards Used</span></span>](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
