---
title: "Преобразование типов XML-данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d2f5f5d27b3d21ff12f5eea7613e80e73c5b6597
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="conversion-of-xml-data-types"></a>Преобразование типов XML-данных
Большинство методов найден в **XmlConvert** класса используются для преобразования данных между строками и строго типизированными форматами. Методы не зависят от языковых стандартов. Это означает, что при преобразовании они не принимают во внимание параметры языковых стандартов.  
  
## <a name="reading-string-as-types"></a>Считывание строк как типов  
 Следующий пример считывает строку и преобразует ее в **DateTime** типа.  
  
 Заданы следующие входные XML-данные:  
  
 **Ввод**  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 Этот код преобразует строку в **DateTime** формат:  
  
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
 Следующий образец считывает **Int32** и преобразуется в строку.  
  
 Заданы следующие входные XML-данные:  
  
 **Ввод**  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 Этот код преобразует **Int32** в **строка**:  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a>См. также  
 [Преобразование строк в типы данных .NET Framework](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
 [Преобразование типов .NET Framework в строки](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
