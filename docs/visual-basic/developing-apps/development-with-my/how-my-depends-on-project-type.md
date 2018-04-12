---
title: Зависимость My от типа проекта (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a37bf43096931597278974099becb9be6ae133d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Зависимость My от типа проекта (Visual Basic)
`My`предоставляет только те объекты, необходимые для конкретного типа проекта. Например `My.Forms` объекта, доступные в приложении Windows Forms, но не доступен в консольном приложении. В этом разделе описывается, что `My` доступных объектов в различных типах проектов.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>Мои в Windows приложения и веб-сайтов  
 `My`предоставляет только те объекты, которые полезны в текущем типе проекта; он подавляет объекты, которые не применяются. Например, на следующем рисунке показана `My` объектной модели в проекте Windows Forms.  
  
 ![Форма My в приложение Windows Forms](../../../visual-basic/developing-apps/development-with-my/media/myinwinform.png "MyInWinForm")  
  
 В проекте веб-сайта `My` предоставляет объекты, относящиеся к веб-разработчиком (такие как `My.Request` и `My.Response` объектов) при подавлении объекты, которые не являются значимыми (такие как `My.Forms` объекта). На следующем рисунке показана `My` объектной модели в проект веб-сайта:  
  
 ![Форма My в веб-приложении](../../../visual-basic/developing-apps/development-with-my/media/myinweb.png "MyInWeb")  
  
## <a name="project-details"></a>Сведения о проекте  
 В следующей таблице показаны которой `My` объекты, включенные по умолчанию для восьми типов проектов: Windows приложения, библиотеки типов, консольное приложение, Windows библиотеки элементов управления, Web Библиотека элементов управления, Windows службы, пустым и веб-сайта.  
  
 Существуют три версии `My.Application` объект, две версии `My.Computer` объекта и две версии `My.User` объекта; сведения об этих версиях приведены в сноски после таблицы.  
  
|My-объект|Приложение Windows|Библиотека классов|Консольное приложение|Библиотека элементов управления Windows|Библиотека веб-элементов управления|Служба Windows|Empty|Веб-сайт|  
|---|---|---|---|---|---|---|---|---|  
|`My.Application`|**Да** <sup>1</sup>|**Да** <sup>2</sup>|**Да** <sup>3</sup>|**Да** <sup>2</sup>|Нет|**Да** <sup>3</sup>|Нет|Нет|  
|`My.Computer`|**Да** <sup>4</sup>|**Да** <sup>4</sup>|**Да** <sup>4</sup>|**Да** <sup>4</sup>|**Да** <sup>5</sup>|**Да** <sup>4</sup>|Нет|**Да** <sup>5</sup>|  
|`My.Forms`|**Да**|Нет|Нет|**Да**|Нет|Нет|Нет|Нет|  
|`My.Log`|Нет|Нет|Нет|Нет|Нет|Нет|Нет|**Да**|  
|`My.Request`|Нет|Нет|Нет|Нет|Нет|Нет|Нет|**Да**|  
|`My.Resources`|**Да**|**Да**|**Да**|**Да**|**Да**|**Да**|Нет|Нет|  
|`My.Response`|Нет|Нет|Нет|Нет|Нет|Нет|Нет|**Да**|  
|`My.Settings`|**Да**|**Да**|**Да**|**Да**|**Да**|**Да**|Нет|Нет|  
|`My.User`|**Да** <sup>6</sup>|**Да** <sup>6</sup>|**Да** <sup>6</sup>|**Да** <sup>6</sup>|**Да** <sup>7</sup>|**Да** <sup>6</sup>|Нет|**Да** <sup>7</sup>|  
|`My.WebServices`|**Да**|**Да**|**Да**|**Да**|**Да**|**Да**|Нет|Нет|  
  
 <sup>1</sup> версию Windows Forms `My.Application`. Является производной от версии консоли (см. Примечание 3). Добавляет поддержку для взаимодействия с окнами приложения и предоставляет [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] модели приложения.  
  
 <sup>2</sup> версии библиотеки `My.Application`. Предоставляет базовые функциональные возможности, необходимые приложению: содержит элементы для записи в журнал приложений и доступом к данным приложения.  
  
 <sup>3</sup> версию консоли `My.Application`. Является производным от версии библиотеки (см. Примечание 2), и добавляет дополнительные элементы для доступа к аргументы командной строки и сведения о развертывании ClickOnce для приложения.  
  
 <sup>4</sup> версия Windows `My.Computer`. Является производным от версии сервера (см. Примечание 5) и предоставляет доступ к полезным объектам на клиентском компьютере, например экрана, клавиатуры и мыши.  
  
 <sup>5</sup> серверной версии `My.Computer`. Основные сведения о компьютере, такие как имя, доступ к времени и т. д.  
  
 <sup>6</sup> версия Windows `My.User`. Этот объект связан с идентификатором текущего потока.  
  
 <sup>7</sup> веб-версия `My.User`. Этот объект связан с удостоверением пользователя текущего HTTP-запроса приложения.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.Logging.Log>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)  
 [Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)  
 [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
