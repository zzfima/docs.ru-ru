---
title: Преобразование типов XML-данных
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 56b5b51848858b7f1240059ca30eb48474650b73
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555132"
---
# <a name="conversion-of-xml-data-types"></a>Преобразование типов XML-данных
Большая часть методов класса **XmlConvert** используются для преобразования данных в строки и строго типизированные форматы. Методы не зависят от языковых стандартов. Это означает, что при преобразовании они не принимают во внимание параметры языковых стандартов.  
  
## <a name="reading-string-as-types"></a>Считывание строк как типов  
 Следующий образец считывает строку и преобразует ее в тип **DateTime**.  
  
 Заданы следующие входные XML-данные:  
  
 **Ввод**  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 Этот код преобразует строку в формат **DateTime**:  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a>Запись строк как типов  
 Следующий пример считывает значение типа **Int32** и преобразует его в строку.  
  
 Заданы следующие входные XML-данные:  
  
 **Ввод**  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 Этот код преобразует данные типа **Int32** в тип **String**:  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a>См. также

- [Преобразование строк в типы данных .NET Framework](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
- [Преобразование типов .NET Framework в строки](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
