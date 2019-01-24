---
title: Работа с динамическими объектами (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 14bd78f2897edc9f2092e062fda16ba5a7d04c37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640866"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Работа с динамическими объектами (Visual Basic)
Динамические объекты предоставляют другой способ, отличное от `Object` типа, чтобы позднего связывания с объектом во время выполнения. Динамический объект предоставляет члены, такие как свойства и методы во время выполнения с помощью динамических интерфейсов, которые определены в <xref:System.Dynamic> пространства имен. Можно использовать классы в <xref:System.Dynamic> пространства имен для создания объектов, которые работают со структурами данных, которые не соответствуют статическому типу или формату. Можно также использовать динамические объекты, которые определены в динамических языках, таких как IronPython и IronRuby. Примеры, показывающие, как создавать динамические объекты или использовать динамический объект, определенный в динамических языков, см. в разделе [Пошаговое руководство: Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, или <xref:System.Dynamic.ExpandoObject>.  
  
 Visual Basic выполняет привязку к объектам из среды выполнения динамического языка и динамических языков, таких как IronPython и IronRuby, используя <xref:System.Dynamic.IDynamicMetaObjectProvider> интерфейс. Примеры классов, реализующих `IDynamicMetaObjectProvider` интерфейс расположены <xref:System.Dynamic.DynamicObject> и <xref:System.Dynamic.ExpandoObject> классы.  
  
 Если вызов с поздним связыванием выполняется на объект, который реализует `IDynamicMetaObjectProvider` интерфейс, Visual Basic привязки к динамическому объекту с помощью этого интерфейса. Если вызов с поздним связыванием выполняется на объект, который не реализует `IDynamicMetaObjectProvider` интерфейс, или, если вызов `IDynamicMetaObjectProvider` интерфейс завершается со сбоем, Visual Basic выполняет привязку к объекту с помощью позднего связывания возможности среды выполнения Visual Basic.  
  
## <a name="see-also"></a>См. также
- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [Пошаговое руководство: Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
