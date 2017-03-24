---
title: "Работа с динамическими объектами (Visual Basic) | Документы Microsoft"
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
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 366b563764baaa39849356a782ecee264b2ae94f
ms.lasthandoff: 03/13/2017

---
# <a name="working-with-dynamic-objects-visual-basic"></a>Работа с динамическими объектами (Visual Basic)
Динамические объекты предоставляют другой способ, отличного от `Object` тип позднего связывания объекта во время выполнения. Динамический объект предоставляет элементы, такие как свойства и методы во время выполнения, используя динамический интерфейс, которые определены в <xref:System.Dynamic>имен.</xref:System.Dynamic> Можно использовать классы в <xref:System.Dynamic>пространство имен для создания объектов, работающих со структурами данных, не соответствующими статическому типу или формату.</xref:System.Dynamic> Можно также использовать динамические объекты, определенные в динамических языках, таких как IronPython и IronRuby. Примеры, демонстрирующие способы создания динамических объектов или использовать динамического объекта, определенного на динамическом языке см. в разделе [Пошаговое руководство: создание с помощью динамических объектов и](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, или <xref:System.Dynamic.ExpandoObject>.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]создает привязку к объектам среды выполнения динамических языков и динамических языков, таких как IronPython и IronRuby, используя <xref:System.Dynamic.IDynamicMetaObjectProvider>интерфейса.</xref:System.Dynamic.IDynamicMetaObjectProvider> Примеры классов, реализующих `IDynamicMetaObjectProvider` интерфейс — <xref:System.Dynamic.DynamicObject>и <xref:System.Dynamic.ExpandoObject>классы.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject>  
  
 Если объект, реализующий производится вызов с поздним связыванием `IDynamicMetaObjectProvider` интерфейс, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] привязывается к динамическому объекту с помощью этого интерфейса. Если вызов с поздним связыванием объект, который не реализует `IDynamicMetaObjectProvider` интерфейс, или, если вызов `IDynamicMetaObjectProvider` интерфейс завершается ошибкой, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] привязывается к объекту с помощью возможностей позднего связывания [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] среды выполнения.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Dynamic.DynamicObject></xref:System.Dynamic.DynamicObject>   
 <xref:System.Dynamic.ExpandoObject></xref:System.Dynamic.ExpandoObject>   
 [Пошаговое руководство: Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)   
 [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
