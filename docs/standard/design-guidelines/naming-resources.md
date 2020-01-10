---
title: Именование ресурсов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: b64a3ef6e12f8ea1abf7efd9c22f2f4333dda5c8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709170"
---
# <a name="naming-resources"></a>Именование ресурсов
Так как на локализуемые ресурсы можно ссылаться через определенные объекты, как если бы они были свойствами, рекомендации по именованию ресурсов похожи на правила свойств.  
  
 **✓ DO** использовать PascalCasing в ключи ресурсов.  
  
 **✓ DO** предоставляют описательные, а не короткие идентификаторы.  
  
 **X DO NOT** использовать зарезервированные слова языка основных языков среды CLR.  
  
 **✓ DO** использовать только буквы, цифры и знаки подчеркивания, при именовании ресурсов.  
  
 **✓ DO** используется следующее соглашение об именовании ресурсов сообщение исключения.  
  
 Идентификатор ресурса должен быть именем типа исключения и коротким идентификатором исключения:  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также:

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)
