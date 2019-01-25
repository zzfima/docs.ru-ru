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
author: KrzysztofCwalina
ms.openlocfilehash: 44627aafd9ec779625413a0862412a8f6c408109
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497609"
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
  
 *Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)
