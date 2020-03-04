---
title: Базовая сериализация
ms.date: 03/30/2017
helpviewer_keywords:
- binary serialization, basic serialization
- serialization, basic serialization
ms.assetid: d899d43c-335a-433e-a589-cd187192984f
dev_langs:
- CSharp
ms.openlocfilehash: a2dde9f795dfe31ff6ef821272a0d5e8d20e8b2f
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159953"
---
# <a name="basic-serialization"></a>Базовая сериализация

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

Самый простой способ создать сериализуемый класс — отметить его атрибутом <xref:System.SerializableAttribute> следующим образом.  
  
```csharp  
[Serializable]  
public class MyObject {  
  public int n1 = 0;  
  public int n2 = 0;  
  public String str = null;  
}  
```  
  
В следующем примере кода показано, как экземпляр этого класса можно сериализовать в файл.  
  
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
  
В этом примере для сериализации используется двоичный модуль форматирования. Все, что нужно сделать, — создать экземпляр потока и модуль форматирования, который будет использоваться, а затем вызвать для модуля форматирования метод **Serialize**. Сериализуемый поток и объект для этого вызова предоставляются как параметры. Хотя в этом примере это явно не показано, будут сериализованы все переменные членов класса - даже переменные, отмеченные как закрытые. Таким образом, двоичная сериализация отличается от класса <xref:System.Xml.Serialization.XmlSerializer>, при котором выполняется сериализация только открытых полей. Сведения об исключении переменных членов из двоичной сериализации см. в разделе [Выборочная сериализация](selective-serialization.md).  
  
Не менее просто и восстановление объекта в предыдущее состояние. Сначала создайте поток для чтения и <xref:System.Runtime.Serialization.Formatter>, а затем дайте модулю форматирования команду десериализовать объект. Эта процедура показана в следующем примере кода.  
  
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
  
Используемый выше <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> очень эффективен и генерирует компактный поток байтов. Все сериализуемые с использованием этого модуля форматирования объекты можно также десериализовать с его помощью, что делает его идеальным инструментом для сериализации объектов, которые будут десериализованы в платформе .NET Framework. Важно отметить, что во время десериализации объекта конструкторы не вызываются. Это ограничение накладывается на десериализацию по причинам обеспечения производительности. Однако при этом способе нарушаются некоторые обычные контракты, которые осуществляет среда выполнения с использованием модуля записи объектов, и разработчики, отмечая объект как сериализуемый, должны понимать последствия.  
  
Если требуется обеспечение переносимости, используйте <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>. Просто замените **BinaryFormatter** в коде выше на **SoapFormatter** и вызовите **Serialize** и **Deserialize**, как и раньше. Результатом работы этого модуля форматирования в примере выше является следующее.  
  
```xml  
<SOAP-ENV:Envelope  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
  SOAP-ENV:encodingStyle=  
  "http://schemas.microsoft.com/soap/encoding/clr/1.0"  
  "http://schemas.xmlsoap.org/soap/encoding/"  
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
  
Важно отметить, что атрибут [Serializable](xref:System.SerializableAttribute) не может быть унаследован. Если новый класс наследуется от `MyObject`, новый класс также должен быть отмечен атрибутом, иначе его сериализация невозможна. Например, при попытке сериализовать экземпляр класса (см. ниже) будет выдано исключение <xref:System.Runtime.Serialization.SerializationException>, информирующее о том, что тип `MyStuff` не отмечен как сериализуемый.  
  
```csharp  
public class MyStuff : MyObject
{  
  public int n3;  
}  
```  
  
 Использование атрибута [Serializable](xref:System.SerializableAttribute) удобно, но у него есть свои ограничения, как это показано выше. См. раздел [Правила сериализации](serialization-guidelines.md), чтобы получить сведения о том, в каких случаях класс следует отмечать для сериализации. Сериализацию невозможно добавить в класс после его компиляции.  
  
## <a name="see-also"></a>См. также раздел

- [Двоичная сериализация](binary-serialization.md)
- [Сериализация XML и SOAP](xml-and-soap-serialization.md)
