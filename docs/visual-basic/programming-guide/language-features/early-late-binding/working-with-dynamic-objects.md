---
title: Работа с динамическими объектами
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 20d007fb48e1db352bab6d8e25d2e60e02554732
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345164"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Работа с динамическими объектами (Visual Basic)
Динамические объекты предоставляют другой способ, отличный от типа `Object`, для позднего связывания с объектом во время выполнения. Динамический объект предоставляет элементы, такие как свойства и методы, во время выполнения с помощью динамических интерфейсов, определенных в пространстве имен <xref:System.Dynamic>. Классы в пространстве имен <xref:System.Dynamic> можно использовать для создания объектов, работающих с структурами данных, которые не соответствуют статическому типу или формату. Кроме того, можно использовать динамические объекты, определенные на динамических языках, таких как IronPython и IronRuby. Примеры, демонстрирующие создание динамических объектов или использование динамического объекта, определенного в динамическом языке, см. в разделе [Пошаговое руководство. Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>или <xref:System.Dynamic.ExpandoObject>.  
  
 Visual Basic выполняет привязку к объектам из среды выполнения динамического языка и динамических языков, таких как IronPython и IronRuby, с помощью интерфейса <xref:System.Dynamic.IDynamicMetaObjectProvider>. Примерами классов, реализующих интерфейс `IDynamicMetaObjectProvider`, являются классы <xref:System.Dynamic.DynamicObject> и <xref:System.Dynamic.ExpandoObject>.  
  
 Если вызов с поздним связыванием выполняется с объектом, реализующим интерфейс `IDynamicMetaObjectProvider`, Visual Basic привязывается к динамическому объекту с помощью этого интерфейса. Если вызов с поздним связыванием выполняется с объектом, который не реализует интерфейс `IDynamicMetaObjectProvider`, или если вызов `IDynamicMetaObjectProvider`ного интерфейса завершается неудачей, Visual Basic привязывается к объекту с помощью возможностей позднего связывания среды выполнения Visual Basic.  
  
## <a name="see-also"></a>См. также

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [Пошаговое руководство. Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
