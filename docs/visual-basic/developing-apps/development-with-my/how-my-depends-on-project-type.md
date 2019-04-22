---
title: Зависимость My от типа проекта (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
ms.openlocfilehash: 743160889c4f24a9edb2d0f9799662a74c5061fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842087"
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Зависимость My от типа проекта (Visual Basic)
`My` предоставляет только те объекты, необходимые для конкретного типа проекта. Например `My.Forms` объекта, доступные в приложении Windows Forms, но не доступен в консольном приложении. В этом разделе описывается, что `My` объекты доступны в различных типов проектов.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>Мои в Windows приложений и веб-сайтов  
 `My` предоставляет только те объекты, которые полезны в текущем типе проекта; Подавляет объекты, которые не применяются. Например, на следующем рисунке показана `My` объектной модели в проекте Windows Forms.  
  
 ![Форма My в приложении Windows Forms](../../../visual-basic/developing-apps/development-with-my/media/myinwinform.png "MyInWinForm")  
  
 В проекте веб-сайта `My` предоставляет объекты, относящиеся к веб-разработчик (такие как `My.Request` и `My.Response` объектов) при подавлении объекты, не относящиеся (такие как `My.Forms` объекта). На следующем рисунке показана `My` объектной модели в проекте веб-сайта:  
  
 ![Форма My в веб-приложении](../../../visual-basic/developing-apps/development-with-my/media/myinweb.png "MyInWeb")  
  
## <a name="project-details"></a>Сведения о проекте  
 В следующей таблице показано, что `My` объекты включены по умолчанию для восьми типов проектов: Приложения Windows, библиотеки типов, консольное приложение, Windows библиотеки элементов управления, Web Библиотека элементов управления, Windows службы, пустой и веб-сайта.  
  
 Существуют три версии `My.Application` object, две версии `My.Computer` объекта и две версии `My.User` объекта; сведения об этих версиях приведены в сносках после таблицы.  
  
|Объект|Приложение Windows|Библиотека классов|Консольное приложение|Библиотека элементов управления Windows|Web Control Library|Служба Windows|Empty|Веб-сайт|  
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
  
 <sup>1</sup> версии Windows Forms `My.Application`. Является производным от версии консоли (см. Примечание 3). добавлена поддержка для взаимодействия с окнами приложения и предоставляет модель приложения Visual Basic.  
  
 <sup>2</sup> версии библиотеки `My.Application`. Предоставляет базовые функциональные возможности, необходимые приложению: предоставляет члены для записи в журнал приложений и доступ к сведениям о приложении.  
  
 <sup>3</sup> версию консоли `My.Application`. Является производным от версии библиотеки (см. Примечание 2), и добавляет дополнительные члены для доступа к аргументы командной строки и сведения о развертывании ClickOnce для приложения.  
  
 <sup>4</sup> Windows версии `My.Computer`. Является производным от версии сервера (см. Примечание 5) и предоставляет доступ к полезным объектам на клиентском компьютере, например экрана, клавиатуры и мыши.  
  
 <sup>5</sup> серверная версия `My.Computer`. Содержит основные сведения о компьютере, такие как имя, доступ к часам и т. д.  
  
 <sup>6</sup> Windows версии `My.User`. Этот объект связан с удостоверение текущего потока.  
  
 <sup>7</sup> веб-версии `My.User`. Этот объект связан с удостоверением пользователя текущего HTTP-запроса приложения.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
- [Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)
- [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
