---
title: "Отражение (C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ab40ab2258703670576084eccf7fd7e1b113d08d
ms.lasthandoff: 03/13/2017

---
# <a name="reflection-c"></a>Отражение (C#)
Механизм отражения позволяет получать объекты (типа <xref:System.Type>), которые описывают сборки, модули и типы. Отражение можно использовать для динамического создания экземпляра типа, привязки типа к существующему объекту, а также получения типа из существующего объекта и вызова его методов или доступа к его полям и свойствам. Если в коде используются атрибуты, отражение обеспечивает доступ к ним. Дополнительные сведения см. в разделе [Атрибуты](https://msdn.microsoft.com/library/5x6cd29c).  
  
 Вот простой пример отражения, в котором для получения типа переменной используется статический метод `GetType`, наследуемый всеми типами от базового класса `Object`.  
  
```csharp  
// Using GetType to obtain type information:  
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type);  
```  
  
 Результат.  
  
 `System.Int32`  
  
 В этом примере отражение используется для получения полного имени загруженной сборки.  
  
```csharp  
// Using Reflection to get information from an Assembly:  
System.Reflection.Assembly info = typeof(System.Int32).Assembly;  
System.Console.WriteLine(info);  
```  
  
 Результат.  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
> [!NOTE]
>  Ключевые слова C# `protected` и `internal` не имеют никакого значения в промежуточном языке и не используются в интерфейсах API отражения. Соответствующими терминами в промежуточном языке являются *Family* и *Assembly*. Для идентификации метода `internal` с помощью отражения используется свойство <xref:System.Reflection.MethodBase.IsAssembly%2A>. Для идентификации метода `protected internal` используется свойство <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.  
  
## <a name="reflection-overview"></a>Общие сведения об отражении  
 Отражение удобно использовать в следующих ситуациях:  
  
-   При необходимости доступа к атрибутам в метаданных программы. Дополнительные сведения см. в разделе [Извлечение информации, сохраненной в атрибуте](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c).  
  
-   Для проверки и создания экземпляров типов в сборке.  
  
-   Для создания типов во время выполнения. Используйте классы в <xref:System.Reflection.Emit>.  
  
-   Для выполнения позднего связывания, которое обеспечивает доступ к методам в типах, созданных во время выполнения. См. раздел [Динамическая загрузка и использование типов](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc).  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения:  
  
-   [Отражение](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)  
  
-   [Просмотр сведений о типах](http://msdn.microsoft.com/library/7e7303a9-4064-4738-b4e7-b75974ed70d2)  
  
-   [Отражение и универсальные типы](http://msdn.microsoft.com/library/f7180fc5-dd41-42d4-8a8e-1b34288e06de)  
  
-   <xref:System.Reflection.Emit>  
  
-   [Извлечение информации, сохраненной в атрибуте](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Сборки в среде CLR](https://msdn.microsoft.com/library/k3677y81)
