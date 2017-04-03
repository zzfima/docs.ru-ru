---
title: "Универсальные типы и отражение (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], reflection
- reflection [C#], generic types
ms.assetid: 162fd9b4-dd5b-4abb-8c9b-e44e21e2f451
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cea1f48f336e4c73fa317d1cbbab3d06ceb6045f
ms.lasthandoff: 03/13/2017

---
# <a name="generics-and-reflection-c-programming-guide"></a>Универсальные типы и отражение (Руководство по программированию в C#)
Поскольку среда CLR имеет доступ к данным универсальных типов во время выполнения, вы можете использовать отражение для получения сведений об универсальных типах точно так же, как и для неуниверсальных типов. Дополнительные сведения см. в разделе [Универсальные типы во время выполнения](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
 В [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)] в класс <xref:System.Type> добавлено несколько новых членов для поддержки данных времени выполнения для универсальных типов. Дополнительные сведения о том, как использовать эти методы и свойства, см. в документации по этим классам. Пространство имен <xref:System.Reflection.Emit> также содержит новые члены, которые поддерживают универсальные типы. См. статью [Практическое руководство. Определение универсального типа с порождаемым отражением](http://msdn.microsoft.com/library/07d5f01a-7b5b-40ea-9b15-f21561098fe4).  
  
 Список неизменяемых условий для терминов, используемых в отражении универсальных типов, см. в примечаниях к описанию свойства <xref:System.Type.IsGenericType%2A>.  
  
|Имя члена System.Type|Описание|  
|-----------------------------|-----------------|  
|<xref:System.Type.IsGenericType%2A>|Возвращает значение true, если тип является универсальным.|  
|<xref:System.Type.GetGenericArguments%2A>|Возвращает массив объектов `Type`, которые представляют аргументы типа, предоставленные для создаваемого типа, или параметры определения универсального типа.|  
|<xref:System.Type.GetGenericTypeDefinition%2A>|Возвращает базовое определение универсального типа для текущего создаваемого типа.|  
|<xref:System.Type.GetGenericParameterConstraints%2A>|Возвращает массив объектов `Type`, которые представляют ограничения, накладываемые на параметр текущего универсального типа.|  
|<xref:System.Type.ContainsGenericParameters%2A>|Возвращает значение true, если тип или любые включающие его типы или методы содержат параметры типа, для которых конкретные типы не предоставлены.|  
|<xref:System.Type.GenericParameterAttributes%2A>|Получает сочетание флагов `GenericParameterAttributes`, описывающих особые ограничения текущего параметра универсального типа.|  
|<xref:System.Type.GenericParameterPosition%2A>|Для объекта `Type`, представляющего параметр типа, получает позицию параметра типа в списке параметров определения универсального типа или метода, который объявил параметр типа.|  
|<xref:System.Type.IsGenericParameter%2A>|Получает значение, позволяющее определить, представляет ли текущий объект `Type` параметр типа для определения универсального типа или метода.|  
|<xref:System.Type.IsGenericTypeDefinition%2A>|Получает значение, определяющее, представляет ли текущий объект <xref:System.Type> определение универсального типа, на основе которого можно конструировать другие универсальные типы. Возвращает значение true, если тип представляет определение универсального типа.|  
|<xref:System.Type.DeclaringMethod%2A>|Возвращает универсальный метод, который определяет параметр текущего универсального типа, или значение null, если параметр типа не был определен универсальным методом.|  
|<xref:System.Type.MakeGenericType%2A>|Замещает элементы массива типов для параметров определения текущего универсального типа и возвращает объект <xref:System.Type>, представляющий итоговый сконструированный тип.|  
  
 Кроме того, в класс <xref:System.Reflection.MethodInfo> добавлены новые члены для поддержки данных времени выполнения для универсальных методов. Список неизменяемых условий для терминов, используемых для отражения универсальных методов, см. в примечаниях к описанию свойства <xref:System.Reflection.MethodInfo.IsGenericMethod%2A>.  
  
|Имя члена System.Reflection.MemberInfo|Описание|  
|----------------------------------------------|-----------------|  
|<xref:System.Reflection.MethodInfo.IsGenericMethod%2A>|Возвращает значение true, если метод является универсальным.|  
|<xref:System.Reflection.MethodInfo.GetGenericArguments%2A>|Возвращает массив объектов Type, которые представляют аргументы создаваемого универсального метода, относящиеся к типу, или параметры типа определения универсального метода.|  
|<xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A>|Возвращает базовое определение универсального метода для текущего создаваемого метода.|  
|<xref:System.Reflection.MethodInfo.ContainsGenericParameters%2A>|Возвращает значение true, если метод или любые включающие его типы содержат параметры типа, для которых конкретные типы не предоставлены.|  
|<xref:System.Reflection.MethodInfo.IsGenericMethodDefinition%2A>|Возвращает значение true, если текущий объект <xref:System.Reflection.MethodInfo> представляет определение универсального метода.|  
|<xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>|Заменяет параметры типа элементами массива типов для определения текущего универсального метода и возвращает объект <xref:System.Reflection.MethodInfo>, представляющий итоговый сконструированный метод.|  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)   
 [Отражение и универсальные типы](http://msdn.microsoft.com/library/f7180fc5-dd41-42d4-8a8e-1b34288e06de)   
 [Универсальные шаблоны](https://msdn.microsoft.com/library/ms172192)
