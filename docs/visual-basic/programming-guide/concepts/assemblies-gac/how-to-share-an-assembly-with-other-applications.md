---
title: "Как: совместное использование сборки с другими приложениями (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0ad7a3f2ee82d0a582e755035448d565a9a8cb9d
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a>Как: совместное использование сборки с другими приложениями (Visual Basic)
Сборки могут быть закрытыми или общими. По умолчанию большинство простых программ состоят из закрытой сборки, так как она не предназначена для использования другими приложениями.  
  
 Для совместного использования сборки с другими приложениями ее необходимо поместить в [глобальный кэш сборок](../../../../framework/app-domains/gac.md) (GAC).  
  
### <a name="sharing-an-assembly"></a>Предоставление общего доступа к сборке  
  
1.  Создайте сборку. Дополнительные сведения см. в разделе [Создание сборок](../../../../framework/app-domains/create-assemblies.md).  
  
2.  Назначьте сборке строгое имя. Дополнительные сведения см. в разделе [Практическое руководство. Подписание сборки строгим именем](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
3.  Назначьте сведения о версии для сборки. Дополнительные сведения см. в разделе [Версии сборок](../../../../../docs/framework/app-domains/assembly-versioning.md).  
  
4.  Добавьте сборку в глобальный кэш сборок. Дополнительные сведения см. в разделе [Практическое руководство. Установка сборки в глобальный кэш сборок](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).  
  
5.  Получите доступ к типам, содержащимся в сборке, из других приложений. Дополнительные сведения см. в разделе [Практическое руководство. Создание ссылки на сборку со строгим именем](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).  
  
## <a name="see-also"></a>См. также  
 [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md) [сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Программирование с использованием сборок](../../../../framework/app-domains/programming-with-assemblies.md)
