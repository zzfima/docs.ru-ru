---
title: "Как Мой зависит от типа проекта (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
caps.latest.revision: 18
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d193dade94980f04b31605ea6fa968f9fa7d0ad6
ms.lasthandoff: 03/13/2017

---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Зависимость My от типа проекта (Visual Basic)
`My`предоставляет только те объекты, необходимые для конкретного типа проекта. Например `My.Forms` объект в приложении Windows Forms, но не доступен в консольном приложении. В этом разделе описывается, которой `My` объекты будут доступны в различных типах проектов.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>Мои в Windows приложений и веб-сайтов  
 `My`предоставляет только те объекты, которые полезны в текущем типе проекта; он отключает объекты, которые не применяются. Например, на следующем рисунке показана `My` объектной модели в проекте Windows Forms.  
  
 ![Форма My в приложение Windows Forms](../../../visual-basic/developing-apps/development-with-my/media/myinwinform.png "MyInWinForm")  
  
 В проект веб-сайта `My` предоставляет объекты, относящиеся к веб-разработчик (такие как `My.Request` и `My.Response` объектов) при подавлении объекты, которые не являются значимыми (такие как `My.Forms` объект). На следующем рисунке показана `My` объектной модели в проект веб-сайта:  
  
 ![Форма My в веб-приложении](../../../visual-basic/developing-apps/development-with-my/media/myinweb.png "MyInWeb")  
  
## <a name="project-details"></a>Сведения о проекте  
 В следующей таблице показаны которого `My` объекты, включенные по умолчанию для восьми типов проектов: Windows приложения, библиотеки типов, консольного приложения, Windows библиотеки элементов управления, Web библиотеки элементов управления, Windows службы, пустой и веб-сайта.  
  
 Существуют три версии `My.Application` объект, две версии `My.Computer` объекта и две версии `My.User` объекта; сведения об этих версиях приведены в сносках после таблицы.  
  
|My-объект|Приложение Windows|Библиотека классов|Консольное приложение|Библиотека элементов управления Windows|Библиотека веб-элементов управления|Служба Windows|Empty|Веб-сайт|  
|---|---|---|---|---|---|---|---|---|  
|`My.Application`|**Yes** <sup>1</sup>|**Yes** <sup>2</sup>|**Yes** <sup>3</sup>|**Yes** <sup>2</sup>|Нет|**Yes** <sup>3</sup>|Нет|Нет|  
|`My.Computer`|**Yes** <sup>4</sup>|**Yes** <sup>4</sup>|**Yes** <sup>4</sup>|**Yes** <sup>4</sup>|**Yes** <sup>5</sup>|**Yes** <sup>4</sup>|Нет|**Yes** <sup>5</sup>|  
|`My.Forms`|**Да**|Нет|Нет|**Да**|Нет|Нет|Нет|Нет|  
|`My.Log`|Нет|Нет|Нет|Нет|Нет|Нет|Нет|**Да**|  
|`My.Request`|Нет|Нет|Нет|Нет|Нет|Нет|Нет|**Да**|  
|`My.Resources`|**Да**|**Да**|**Да**|**Да**|**Да**|**Да**|Нет|Нет|  
|`My.Response`|Нет|Нет|Нет|Нет|Нет|Нет|Нет|**Да**|  
|`My.Settings`|**Да**|**Да**|**Да**|**Да**|**Да**|**Да**|Нет|Нет|  
|`My.User`|**Yes** <sup>6</sup>|**Yes** <sup>6</sup>|**Yes** <sup>6</sup>|**Yes** <sup>6</sup>|**Yes** <sup>7</sup>|**Yes** <sup>6</sup>|Нет|**Yes** <sup>7</sup>|  
|`My.WebServices`|**Да**|**Да**|**Да**|**Да**|**Да**|**Да**|Нет|Нет|  
  
 <sup>1</sup> версии Windows Forms `My.Application`. Является производным от консольной версии (см. Примечание 3). Дополнительно поддерживает взаимодействие с окнами приложения и предоставляет [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] модели приложения.  
  
 <sup>2</sup> версии библиотеки `My.Application`. Предоставляет базовую функциональность, необходимую приложению: предоставляет элементы для записи в журнал приложений и доступе к данным приложения.  
  
 <sup>3</sup> версию консоли `My.Application`. Является производной от версии библиотеки (см. Примечание 2), и добавляет дополнительные члены для доступа к аргументы командной строки приложения и сведения о развертывании ClickOnce.  
  
 <sup>4</sup> версия Windows `My.Computer`. Является производным от версии сервера (см. Примечание 5) и предоставляет доступ к полезным объектам на клиентском компьютере, такие как клавиатуры, экрана и мыши.  
  
 <sup>5</sup> серверной версии `My.Computer`. Основные сведения о компьютере, такие как имя, доступ к времени и т. д.  
  
 <sup>6</sup> версия Windows `My.User`. Этот объект связан с идентификатором текущего потока.  
  
 <sup>7</sup> версия `My.User`. Этот объект связан с удостоверением пользователя текущего HTTP-запроса приложения.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer></xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.Logging.Log></xref:Microsoft.VisualBasic.Logging.Log>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User></xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [Настройка доступа к объектам, доступные в моей](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)   
 [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)   
 [Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)   
 [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
