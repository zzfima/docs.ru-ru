---
title: Именование ресурсов
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5b53fc383e6fc9a5f056bab4eabde9979cd734b
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46493065"
---
# <a name="naming-resources"></a>Именование ресурсов
Так как локализуемые ресурсы можно ссылаться с помощью определенных объектов, как если бы они были свойства, рекомендации по именованию для ресурсов похожи на правила свойств.  
  
 **✓ DO** использовать PascalCasing в ключи ресурсов.  
  
 **✓ DO** предоставляют описательные, а не короткие идентификаторы.  
  
 **X DO NOT** использовать зарезервированные слова языка основных языков среды CLR.  
  
 **✓ DO** использовать только буквы, цифры и знаки подчеркивания, при именовании ресурсов.  
  
 **✓ DO** используется следующее соглашение об именовании ресурсов сообщение исключения.  
  
 Идентификатор ресурса должен быть именем типа исключения, а также краткого идентификатора исключения:  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
- [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)
