---
title: Разработка абстрактных классов
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
caps.latest.revision: 13
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a98c40ccc8005789a3a991bfc93deb11786b8943
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="abstract-class-design"></a>Разработка абстрактных классов
**X не** определение открытого или защищенного внутреннего конструкторов в абстрактных типов.  
  
 Конструкторы должны быть открытыми, только в том случае, если пользователи должны будут создавать экземпляры типа. Так как невозможно создавать экземпляры абстрактного типа, абстрактный тип с открытым конструктором неправильно предназначена и ввести в заблуждение пользователей.  
  
 **✓ СДЕЛАТЬ** Определите защищенный или внутренний конструктор в абстрактных классах.  
  
 Защищенный конструктор, чаще всего и просто позволяет базового класса, чтобы сделать свои собственные инициализации при создании подтипы.  
  
 Внутренний конструктор используется для ограничения конкретные реализации абстрактного класса для сборки, определяющей класс.  
  
 **✓ СДЕЛАТЬ** укажите по крайней мере один конкретный тип, наследующий от каждого абстрактный класс, который можно отправить.  
  
 Это помогает проверить конструктора абстрактного класса. Например <xref:System.IO.FileStream?displayProperty=nameWithType> — это реализация <xref:System.IO.Stream?displayProperty=nameWithType> абстрактного класса.  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по разработке типов](../../../docs/standard/design-guidelines/type.md)  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
