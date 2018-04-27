---
title: Правила разработки членов
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8f4e33735a934b1ac41c34ccb9698c172ada28e1
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="member-design-guidelines"></a>Правила разработки членов
Методы, свойства, события, конструкторы и поля называются членами. Члены могут в конечном счете средства, с помощью которого framework функциональность предоставляется пользователям платформы.  
  
 Члены может быть виртуальными или невиртуальные, конкретная или абстрактными, статический метод или экземпляр и может иметь несколько различных областях специальных возможностей. Этот диапазон предоставляет огромный выразительности, но в то же время требует внимания со стороны конструктора framework.  
  
 В этой главе предоставляет основные правила, которые следует выполнить при разработке члены любого типа.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Перегрузка членов](../../../docs/standard/design-guidelines/member-overloading.md)  
 [Разработка свойств](../../../docs/standard/design-guidelines/property.md)  
 [Разработка конструкторов](../../../docs/standard/design-guidelines/constructor.md)  
 [Разработка событий](../../../docs/standard/design-guidelines/event.md)  
 [Разработка полей](../../../docs/standard/design-guidelines/field.md)  
 [Методы расширения](../../../docs/standard/design-guidelines/extension-methods.md)  
 [Перегрузки операторов](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [Разработка параметров](../../../docs/standard/design-guidelines/parameter-design.md)  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
