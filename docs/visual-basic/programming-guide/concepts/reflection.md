---
title: "Отражение (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3ae042933575849e105d7b681634a61319c1d6ee
ms.lasthandoff: 03/13/2017

---
# <a name="reflection-visual-basic"></a>Отражение (Visual Basic)
Отражение предоставляет объекты (типа <xref:System.Type>), описывающие сборки, модули и типы.</xref:System.Type> Можно использовать отражение для динамически создать экземпляр типа, привязки типа к существующему объекту или получения типа из существующего объекта и вызова его методов или доступа к его полям и свойствам. Если в коде используются атрибуты, отражение позволяет получить к ним доступ. Дополнительные сведения см. в разделе [атрибуты](https://msdn.microsoft.com/library/5x6cd29c).  
  
 Ниже приведен простой пример отражения с помощью статического метода `GetType` - наследуемый всеми типами из `Object` базового класса — для получения типа переменной:  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 Выводится следующий результат:  
  
 `System.Int32`  
  
 В следующем примере отражение используется для получения полного имени загруженной сборки.  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 Выводится следующий результат:  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a>Общие сведения об отражении  
 Отражение полезно в следующих ситуациях:  
  
-   При наличии доступа к атрибутам в метаданных программы. Дополнительные сведения см. в разделе [извлечение информации, сохраненной в атрибуте](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c).  
  
-   Для проверки и создания экземпляров типов в сборке.  
  
-   Для создания новых типов во время выполнения. Используйте классы <xref:System.Reflection.Emit>.</xref:System.Reflection.Emit>  
  
-   Для выполнения позднего связывания, доступ к методам в типах, созданных во время выполнения. См. в разделе [динамическая загрузка и использование типов](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc).  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения:  
  
-   [Отражение](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)  
  
-   [Просмотр сведений о типах](http://msdn.microsoft.com/library/7e7303a9-4064-4738-b4e7-b75974ed70d2)  
  
-   [Отражение и универсальные типы](http://msdn.microsoft.com/library/f7180fc5-dd41-42d4-8a8e-1b34288e06de)  
  
-   <xref:System.Reflection.Emit></xref:System.Reflection.Emit>  
  
-   [Извлечение информации, сохраненной в атрибуте](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)   
 [Сборки в среде CLR](https://msdn.microsoft.com/library/k3677y81)
