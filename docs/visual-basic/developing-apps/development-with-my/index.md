---
title: "Разработка с использованием My (Visual Basic) | Документация Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MyWpfExtension.Windows
dev_langs:
- VB
helpviewer_keywords:
- My object
- My namespace
- My feature
- Visual Basic, programming in
ms.assetid: f1d04509-5e46-4551-9f9f-94334a121fca
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 815f459a651adf98dfb78a8444f4b873dece8283
ms.lasthandoff: 03/13/2017

---
# <a name="development-with-my-visual-basic"></a>Разработка с использованием My (Visual Basic)
Visual Basic предоставляет новые функции для быстрой разработки приложений, которые повышают производительность, упрощают работу и предоставляют богатые возможности. Одна из этих функций, называемая `My`, предоставляет доступ к информации и экземплярам объектов по умолчанию, относящихся к приложению и среде выполнения. Эта информация организована в формате, который обнаруживается через IntelliSense и логически разделен в соответствии с использованием.  
  
 Члены верхнего уровня `My` представляются как объекты. Каждый объект ведет себя как пространство имен или класса с членами `Shared`, предоставляя набор связанных элементов.  
  
 В следующей таблице перечислены объекты `My` верхнего уровня и их связь друг с другом.  
  
 ![Модель объектов для My](../../../visual-basic/developing-apps/development-with-my/media/myobjmodel.gif "MyObjModel")  
  
## <a name="in-this-section"></a>Содержание  
 [Выполнение задач с помощью My.Application, My.Computer и My.User](../../../visual-basic/developing-apps/development-with-my/performing-tasks-with-my-application-my-computer-and-my-user.md)  
 Описывает трех центральных объекта `My`, (`My.Application`, `My.Computer` и `My.User`), которые обеспечивают доступ к информации и функциональным возможностям  
  
 [Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию](../../../visual-basic/developing-apps/development-with-my/default-object-instances-provided-by-my-forms-and-my-webservices.md)  
 Описывает объекты `My.Forms` и `My.WebServices`, которые предоставляют доступ к формам, источникам данных и веб-службам XML, используемым приложениями.  
  
 [Быстрая разработка приложений с использованием My.Resources и My.Settings](../../../visual-basic/developing-apps/development-with-my/rapid-application-development-with-my-resources-and-my-settings.md)  
 Описывает объекты `My.Resources` и `My.Settings`, которые предоставляют доступ к ресурсам и параметрам приложения.  
  
 [Обзор модели приложения в Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 Описывает модель запуска и завершения работы приложения в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 [Зависимость My от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 Предоставляет подробные сведения о том, какие функции `My` доступны в разных типах проектов.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)   
 [Зависимость My от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
