---
title: "Отражение (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8c2ae87eae971129059a7e84b36971c13a5fe71b
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="reflection-visual-basic"></a>Отражение (Visual Basic)
Механизм отражения позволяет получать объекты (типа <xref:System.Type>), которые описывают сборки, модули и типы. Отражение можно использовать для динамического создания экземпляра типа, привязки типа к существующему объекту, а также получения типа из существующего объекта и вызова его методов или доступа к его полям и свойствам. Если в коде используются атрибуты, отражение обеспечивает доступ к ним. Дополнительные сведения см. в разделе [Атрибуты](../../../../docs/standard/attributes/index.md).  
  
 Вот простой пример отражения, в котором для получения типа переменной используется статический метод `GetType`, наследуемый всеми типами от базового класса `Object`.  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 Результат.  
  
 `System.Int32`  
  
 В этом примере отражение используется для получения полного имени загруженной сборки.  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 Результат.  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a>Общие сведения об отражении  
 Отражение удобно использовать в следующих ситуациях:  
  
-   При необходимости доступа к атрибутам в метаданных программы. Дополнительные сведения см. в разделе [Извлечение информации, сохраненной в атрибуте](../../../standard/attributes/retrieving-information-stored-in-attributes.md).  
  
-   Для проверки и создания экземпляров типов в сборке.  
  
-   Для создания типов во время выполнения. Используйте классы в <xref:System.Reflection.Emit>.  
  
-   Для выполнения позднего связывания, которое обеспечивает доступ к методам в типах, созданных во время выполнения. См. раздел [Динамическая загрузка и использование типов](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения:  
  
-   [Отражение](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [Просмотр сведений о типах](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [Отражение и универсальные типы](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [Извлечение информации, сохраненной в атрибуте](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)  
 [Сборки в среде CLR](../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
