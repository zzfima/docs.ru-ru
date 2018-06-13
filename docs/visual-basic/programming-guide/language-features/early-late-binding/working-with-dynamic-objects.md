---
title: Работа с динамическими объектами (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 78b17a379ea219cc24842322703caaa9d29eeb2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647353"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Работа с динамическими объектами (Visual Basic)
Динамические объекты предоставляют другой способ, отличный от `Object` тип позднего связывания объекта во время выполнения. Динамический объект предоставляет элементы, такие как свойства и методы во время выполнения с помощью динамического интерфейсы, которые определены в <xref:System.Dynamic> пространства имен. Можно использовать классы в <xref:System.Dynamic> пространства имен для создания объектов, работающих со структурами данных, которые не соответствуют статический тип или формат. Можно также использовать динамические объекты, которые определены в динамических языках, таких как IronPython и IronRuby. Примеры, демонстрирующие способы создания динамических объектов или использовать динамический объект, определенный в динамической среды см. в разделе [Пошаговое руководство: Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, или <xref:System.Dynamic.ExpandoObject>.  
  
 Visual Basic выполняет привязку к объектам из динамической среды выполнения и динамических языках, таких как IronPython и IronRuby, используя <xref:System.Dynamic.IDynamicMetaObjectProvider> интерфейса. Примеры классов, реализующих `IDynamicMetaObjectProvider` интерфейс — <xref:System.Dynamic.DynamicObject> и <xref:System.Dynamic.ExpandoObject> классы.  
  
 Если вызов с поздним связыванием устанавливается с объектом, реализующим `IDynamicMetaObjectProvider` интерфейс Visual Basic привязывается к динамическому объекту с помощью этого интерфейса. Если выполняется позднего связывания вызов в объект, который не реализует `IDynamicMetaObjectProvider` интерфейса, или, если вызов `IDynamicMetaObjectProvider` интерфейса не удастся, Visual Basic выполняет привязку к объекту с помощью возможностей позднего связывания среды выполнения Visual Basic.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 [Пошаговое руководство. Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)  
 [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
