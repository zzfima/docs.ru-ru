---
title: Зависимость My от типа проекта (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
ms.openlocfilehash: 989329da7dc57cd50b9ce6c88117152d0cb93d66
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775200"
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Зависимость My от типа проекта (Visual Basic)
`My` предоставляет только те объекты, которые необходимы для конкретного типа проекта. Например, объект `My.Forms` доступен в Windows Forms приложении, но недоступен в консольном приложении. В этом разделе описано, какие объекты `My` доступны в различных типах проектов.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>Мои приложения и веб-сайты Windows  
 `My` предоставляет только те объекты, которые полезны в текущем типе проекта; Он подавляет неприменимые объекты. Например, на следующем рисунке показана объектная модель `My` в Windows Formsном проекте.  
  
 ![Схема, показывающая мою объектную модель в приложении Windows Forms.](./media/how-my-depends-on-project-type/my-object-model-windows-forms.png)  
  
 В проекте веб-сайта `My` предоставляет объекты, относящиеся к веб-разработчику (например, объекты `My.Request` и `My.Response`), одновременно поблокируя ненужные объекты (например, объект `My.Forms`). На следующем рисунке показана объектная модель `My` в проекте веб-сайта.  
  
 ![Схема, показывающая мою объектную модель в веб-приложении.](./media/how-my-depends-on-project-type/my-object-model-web.png)  
  
## <a name="project-details"></a>Сведения о проекте  
 В следующей таблице показано, какие `My` объекты включены по умолчанию для восьми типов проектов: приложение Windows, Библиотека классов, консольное приложение, Библиотека элементов управления Windows, Библиотека веб-элементов управления, служба Windows, пустая и веб-сайт.  
  
 Существует три версии объекта `My.Application`, две версии объекта `My.Computer` и две версии объекта `My.User`. сведения об этих версиях приведены в сносках после таблицы.  
  
|Мой объект|Приложение Windows|Библиотека классов|Консольное приложение|Библиотека элементов управления Windows|Библиотека веб-элементов управления|Служба Windows|Empty|Веб-сайт|  
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
  
 <sup>1</sup> Windows Forms версии `My.Application`. Является производным от версии консоли (см. Примечание 3); добавляет поддержку взаимодействия с окнами приложения и предоставляет модель приложения Visual Basic.  
  
 <sup>2</sup> версия библиотеки `My.Application`. Предоставляет базовые функциональные возможности, необходимые для приложения: предоставляет элементы для записи в журнал приложений и доступа к сведениям о приложении.  
  
 <sup>3</sup> консольная версия `My.Application`. Является производным от версии библиотеки (см. Примечание 2) и добавляет дополнительные члены для доступа к аргументам командной строки приложения и сведения о развертывании ClickOnce.  
  
 <sup>4</sup> версия `My.Computer` Windows. Является производным от версии сервера (см. Примечание 5) и предоставляет доступ к полезным объектам на клиентском компьютере, таким как клавиатура, экран и мышь.  
  
 <sup>5</sup> серверная версия `My.Computer`. Предоставляет основные сведения о компьютере, такие как имя, доступ к часам и т. д.  
  
 <sup>6</sup> `My.User` версии Windows. Этот объект связан с текущим удостоверением потока.  
  
 <sup>7</sup> . веб-версия `My.User`. Этот объект связан с удостоверением пользователя текущего HTTP-запроса приложения.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
- [Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)
- [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
