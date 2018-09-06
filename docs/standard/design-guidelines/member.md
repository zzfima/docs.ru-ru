---
title: Правила разработки членов
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1598ac63af38f1ca3e11104bc8e1cd6323d35ed
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43871023"
---
# <a name="member-design-guidelines"></a>Правила разработки членов
Методы, свойства, события, конструкторы и поля в совокупности называются членами. Элементы в конечном счете являются средства, по которому framework функциональность предоставляется конечным пользователям платформы.  
  
 Члены могут быть виртуальными или невиртуальные, конкретные или абстрактными, статический или экземпляр и может иметь несколько различных областях специальных возможностей. Такое разнообразие предоставляет невероятно выразительности, но в то же время требует внимания со стороны конструктор framework.  
  
 В этой главе предлагает основные рекомендации, которые следует выполнить при разработке члены любого типа.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Перегрузка членов](../../../docs/standard/design-guidelines/member-overloading.md)  
 [Разработка свойств](../../../docs/standard/design-guidelines/property.md)  
 [Разработка конструкторов](../../../docs/standard/design-guidelines/constructor.md)  
 [Разработка событий](../../../docs/standard/design-guidelines/event.md)  
 [Разработка полей](../../../docs/standard/design-guidelines/field.md)  
 [Методы расширения](../../../docs/standard/design-guidelines/extension-methods.md)  
 [Перегрузки операторов](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [Разработка параметров](../../../docs/standard/design-guidelines/parameter-design.md)  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
