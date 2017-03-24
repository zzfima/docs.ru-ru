---
title: "Практическое руководство: совместное использование сборки с другими приложениями (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8065a66c8f7c7b9ccb9125b060b0c03cde273482
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a>Практическое руководство: совместное использование сборки с другими приложениями (Visual Basic)
Сборки могут быть закрытыми или общими: по умолчанию, большинство простой программы состоят из закрытой сборки, так как они не предназначены для использования другими приложениями.  
  
 Для совместного использования сборки с другими приложениями, он должен быть помещен в [глобального кэша сборок](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202) (GAC).  
  
### <a name="sharing-an-assembly"></a>Совместное использование сборки  
  
1.  Создайте сборку. Дополнительные сведения см. в разделе [Создание сборки](http://msdn.microsoft.com/library/54832ee9-dca8-4c8b-913c-c0b9d265e9a4).  
  
2.  Назначьте строгое имя сборки. Дополнительные сведения см. в разделе [как: подписать сборку строгим именем](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67).  
  
3.  Укажите сведения о версии для сборки. Дополнительные сведения см. в разделе [управление версиями сборок](https://msdn.microsoft.com/library/51ket42z).  
  
4.  Добавьте сборку в глобальный кэш сборок. Дополнительные сведения см. в разделе [Практическое руководство: Установка сборки в глобальный кэш сборок](http://msdn.microsoft.com/library/a7e6f091-d02c-49ba-b736-7295cb0eb743).  
  
5.  Доступ к типам, содержащихся в сборке из других приложений. Дополнительные сведения см. в разделе [как: ссылки на сборку со строгими именами](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).  
  
## <a name="see-also"></a>См. также  
 [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)
 [сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Программирование с использованием сборок](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)
