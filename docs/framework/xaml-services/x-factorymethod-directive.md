---
title: "Директива x:FactoryMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 0d53db49961c2a75e4547f6b57240cefd2cc17c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="xfactorymethod-directive"></a>Директива x:FactoryMethod
Указывает метод, отличный от конструктора, который процессор XAML должен использовать для инициализации объекта после разрешения его резервного типа.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>Использование атрибута XAML, не x: Arguments  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>Использование атрибута XAML, x: аргументы в виде элементов  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`methodname`|Метод строковое имя метода, который вызывают процессоры XAML для инициализации экземпляра, заданного как `object`. См. заметки.|  
|`oneOrMoreObjectElements`|Один или несколько элементов объекта для объектов, которые задают параметры метода фабрики. Порядок имеет значение; обозначает порядок, в котором аргументы должны быть переданы в метод фабрики.|  
  
## <a name="remarks"></a>Примечания  
 Если `methodname` является методом экземпляра не может быть квалифицирован.  
  
 Поддерживаются статические методы как фабричные методы. Если `methodname` — статический метод `methodname` предоставляется как *typeName*. *имя_метода* сочетания, где *typeName* создается класс, который определяет статический фабричный метод с именем. *typeName* может иметь префикс, если ссылается на тип в сопоставленных xmlns. *typeName* может быть отличается от типа `typeof(``object``)`.  
  
 Фабричный метод должен быть объявлен открытым методом типа, который возвращает соответствующий элемент объекта.  
  
 Фабричный метод должен возвращать экземпляр, который может быть назначен соответствующий объект. Фабричные методы никогда не должен возвращать значение null.  
  
 `x:Arguments`работает по принципу наилучшего соответствия для сигнатур методов фабрик. Сопоставление оценивает количество параметров. Если имеется более одного возможного соответствия для числа параметров, тип параметра является определяется соответствие вычисляется и рекомендации. Если после этого этапа оценки остается неоднозначность, поведение процессора XAML не определено.  
  
 `x:FactoryMethod` Использование элемента не использование элемента свойства в типичных смысле, так как директив разметки не ссылается на объект элемента, содержащего типа. Предполагается, что элементы используются реже, чем использование атрибута. `x:Arguments`(атрибут или элемент) можно использовать вместе с `x:FactoryMethod` использование элемента, но это не отображается в разделах использования.  
  
 `x:FactoryMethod`как элемент должен предшествовать любых других свойств элементов, должны указываться до любых `x:Arguments` также представлены в виде элементов и должен предшествовать любой текст содержимого или внутренний текст и инициализации.  
  
## <a name="see-also"></a>См. также  
 [x:Arguments - директива](../../../docs/framework/xaml-services/x-arguments-directive.md)
