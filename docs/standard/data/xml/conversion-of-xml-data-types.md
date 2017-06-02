---
title: "Преобразование типов XML-данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Преобразование типов XML-данных
Большая часть методов класса **XmlConvert** используются для преобразования данных между строками и строго типизированными форматами.  Методы не зависят от языковых стандартов.  Это означает, что при преобразовании они не принимают во внимание параметры языковых стандартов.  
  
## Считывание строк как типов  
 Следующий образец считывает строку и преобразует ее в тип **DateTime**.  
  
 Заданы следующие входные XML\-данные:  
  
 **Ввод**  
  
```  
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
  
## Запись строк как типов  
 Следующий образец считывает значение типа **Int32** и преобразует его в строку.  
  
 Заданы следующие входные XML\-данные:  
  
 **Ввод**  
  
```  
<TestInt32>-2147483648</TestInt32>  
```  
  
 Этот код преобразует данные типа **Int32** в **String**:  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## См. также  
 [Преобразование строк в типы данных .NET Framework](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)   
 [Преобразование типов .NET Framework в строки](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)