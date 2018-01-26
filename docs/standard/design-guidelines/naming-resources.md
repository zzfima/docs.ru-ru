---
title: "Именование ресурсов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0387d820cc660bdf6cbafb9d76bbf0184c111881
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="naming-resources"></a>Именование ресурсов
Поскольку локализуемые ресурсы можно ссылаться через определенные объекты, как если бы они были свойства, правилам именования для ресурсов похожи на правила свойств.  
  
 **✓ СДЕЛАТЬ** использовать PascalCasing в ключи ресурсов.  
  
 **✓ СДЕЛАТЬ** предоставляют описательные, а не короткие идентификаторы.  
  
 **X не** использовать зарезервированные слова языка основных языков среды CLR.  
  
 **✓ СДЕЛАТЬ** использовать только буквы, цифры и знаки подчеркивания, при именовании ресурсов.  
  
 **✓ СДЕЛАТЬ** используется следующее соглашение об именовании ресурсов сообщение исключения.  
  
 Идентификатор ресурса должен быть именем типа исключения, а также с коротким идентификатором исключения:  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
 [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)
