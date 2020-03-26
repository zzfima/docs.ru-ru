---
title: Базовая сериализация
ms.date: 03/30/2017
helpviewer_keywords:
- binary serialization, basic serialization
- serialization, basic serialization
ms.assetid: d899d43c-335a-433e-a589-cd187192984f
dev_langs:
- CSharp
ms.openlocfilehash: ce86f7897c5c117c4fd6f1eabc4c8b802103261c
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80248034"
---
# <a name="basic-serialization"></a><span data-ttu-id="cb3f1-102">Базовая сериализация</span><span class="sxs-lookup"><span data-stu-id="cb3f1-102">Basic serialization</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="cb3f1-103">Самый простой способ создать сериализуемый класс — отметить его атрибутом <xref:System.SerializableAttribute> следующим образом.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-103">The easiest way to make a class serializable is to mark it with the <xref:System.SerializableAttribute> as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject {  
  public int n1 = 0;  
  public int n2 = 0;  
  public String str = null;  
}  
```  
  
<span data-ttu-id="cb3f1-104">В следующем примере кода показано, как экземпляр этого класса можно сериализовать в файл.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-104">The following code example shows how an instance of this class can be serialized to a file.</span></span>  
  
```csharp  
MyObject obj = new MyObject();  
obj.n1 = 1;  
obj.n2 = 24;  
obj.str = "Some String";  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Create, FileAccess.Write, FileShare.None);  
formatter.Serialize(stream, obj);  
stream.Close();  
```  
  
<span data-ttu-id="cb3f1-105">В этом примере для сериализации используется двоичный модуль форматирования.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-105">This example uses a binary formatter to do the serialization.</span></span> <span data-ttu-id="cb3f1-106">Все, что нужно сделать, — создать экземпляр потока и модуль форматирования, который будет использоваться, а затем вызвать для модуля форматирования метод **Serialize**.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-106">All you need to do is create an instance of the stream and the formatter you intend to use, and then call the **Serialize** method on the formatter.</span></span> <span data-ttu-id="cb3f1-107">Сериализуемый поток и объект для этого вызова предоставляются как параметры.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-107">The stream and the object to serialize are provided as parameters to this call.</span></span> <span data-ttu-id="cb3f1-108">Хотя в этом примере это явно не показано, будут сериализованы все переменные членов класса - даже переменные, отмеченные как закрытые.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-108">Although it is not explicitly demonstrated in this example, all member variables of a class will be serialized—even variables marked as private.</span></span> <span data-ttu-id="cb3f1-109">Таким образом, двоичная сериализация отличается от класса <xref:System.Xml.Serialization.XmlSerializer>, при котором выполняется сериализация только открытых полей.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-109">In this aspect, binary serialization differs from the <xref:System.Xml.Serialization.XmlSerializer> class, which only serializes public fields.</span></span> <span data-ttu-id="cb3f1-110">Сведения об исключении переменных членов из двоичной сериализации см. в разделе [Выборочная сериализация](selective-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="cb3f1-110">For information on excluding member variables from binary serialization, see [Selective Serialization](selective-serialization.md).</span></span>  
  
<span data-ttu-id="cb3f1-111">Не менее просто и восстановление объекта в предыдущее состояние.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-111">Restoring the object back to its former state is just as easy.</span></span> <span data-ttu-id="cb3f1-112">Сначала создайте поток для чтения и <xref:System.Runtime.Serialization.Formatter>, а затем дайте модулю форматирования команду десериализовать объект.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-112">First, create a stream for reading and a <xref:System.Runtime.Serialization.Formatter>, and then instruct the formatter to deserialize the object.</span></span> <span data-ttu-id="cb3f1-113">Эта процедура показана в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-113">The code example below shows how this is done.</span></span>  
  
```csharp  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Open, FileAccess.Read, FileShare.Read);  
MyObject obj = (MyObject) formatter.Deserialize(stream);  
stream.Close();  
  
// Here's the proof.  
Console.WriteLine("n1: {0}", obj.n1);  
Console.WriteLine("n2: {0}", obj.n2);  
Console.WriteLine("str: {0}", obj.str);  
```  
  
<span data-ttu-id="cb3f1-114">Используемый выше <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> очень эффективен и генерирует компактный поток байтов.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-114">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> used above is very efficient and produces a compact byte stream.</span></span> <span data-ttu-id="cb3f1-115">Все сериализуемые с использованием этого модуля форматирования объекты можно также десериализовать с его помощью, что делает его идеальным инструментом для сериализации объектов, которые будут десериализованы в платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-115">All objects serialized with this formatter can also be deserialized with it, which makes it an ideal tool for serializing objects that will be deserialized on the .NET Framework.</span></span> <span data-ttu-id="cb3f1-116">Важно отметить, что во время десериализации объекта конструкторы не вызываются.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-116">It is important to note that constructors are not called when an object is deserialized.</span></span> <span data-ttu-id="cb3f1-117">Это ограничение накладывается на десериализацию по причинам обеспечения производительности.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-117">This constraint is placed on deserialization for performance reasons.</span></span> <span data-ttu-id="cb3f1-118">Однако при этом способе нарушаются некоторые обычные контракты, которые осуществляет среда выполнения с использованием модуля записи объектов, и разработчики, отмечая объект как сериализуемый, должны понимать последствия.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-118">However, this violates some of the usual contracts the runtime makes with the object writer, and developers should ensure that they understand the ramifications when marking an object as serializable.</span></span>  
  
<span data-ttu-id="cb3f1-119">Если требуется обеспечение переносимости, используйте <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-119">If portability is a requirement, use the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> instead.</span></span> <span data-ttu-id="cb3f1-120">Просто замените **BinaryFormatter** в коде выше на **SoapFormatter** и вызовите **Serialize** и **Deserialize**, как и раньше.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-120">Simply replace the **BinaryFormatter** in the code above with **SoapFormatter,** and call **Serialize** and **Deserialize** as before.</span></span> <span data-ttu-id="cb3f1-121">Результатом работы этого модуля форматирования в примере выше является следующее.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-121">This formatter produces the following output for the example used above.</span></span>  
  
```xml  
<SOAP-ENV:Envelope  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
  SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:a1="http://schemas.microsoft.com/clr/assem/ToFile">  
  
  <SOAP-ENV:Body>  
    <a1:MyObject id="ref-1">  
      <n1>1</n1>  
      <n2>24</n2>  
      <str id="ref-3">Some String</str>  
    </a1:MyObject>  
  </SOAP-ENV:Body>  
</SOAP-ENV:Envelope>  
```  
  
<span data-ttu-id="cb3f1-122">Важно отметить, что атрибут [Serializable](xref:System.SerializableAttribute) не может быть унаследован.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-122">It's important to note that the [Serializable](xref:System.SerializableAttribute) attribute cannot be inherited.</span></span> <span data-ttu-id="cb3f1-123">Если новый класс наследуется от `MyObject`, новый класс также должен быть отмечен атрибутом, иначе его сериализация невозможна.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-123">If you derive a new class from `MyObject`, the new class must be marked with the attribute as well, or it cannot be serialized.</span></span> <span data-ttu-id="cb3f1-124">Например, при попытке сериализовать экземпляр класса (см. ниже) будет выдано исключение <xref:System.Runtime.Serialization.SerializationException>, информирующее о том, что тип `MyStuff` не отмечен как сериализуемый.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-124">For example, when you attempt to serialize an instance of the class below, you'll get a <xref:System.Runtime.Serialization.SerializationException> informing you that the `MyStuff` type is not marked as serializable.</span></span>  
  
```csharp  
public class MyStuff : MyObject
{  
  public int n3;  
}  
```  
  
 <span data-ttu-id="cb3f1-125">Использование атрибута [Serializable](xref:System.SerializableAttribute) удобно, но у него есть свои ограничения, как это показано выше.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-125">Using the [Serializable](xref:System.SerializableAttribute) attribute is convenient, but it has limitations as previously demonstrated.</span></span> <span data-ttu-id="cb3f1-126">См. раздел [Правила сериализации](serialization-guidelines.md), чтобы получить сведения о том, в каких случаях класс следует отмечать для сериализации.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-126">Refer to the [Serialization Guidelines](serialization-guidelines.md) for information about when you should mark a class for serialization.</span></span> <span data-ttu-id="cb3f1-127">Сериализацию невозможно добавить в класс после его компиляции.</span><span class="sxs-lookup"><span data-stu-id="cb3f1-127">Serialization cannot be added to a class after it has been compiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb3f1-128">См. также</span><span class="sxs-lookup"><span data-stu-id="cb3f1-128">See also</span></span>

- [<span data-ttu-id="cb3f1-129">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="cb3f1-129">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="cb3f1-130">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="cb3f1-130">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
