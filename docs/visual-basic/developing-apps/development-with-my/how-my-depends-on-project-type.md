---
title: "Зависимость My от типа проекта (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "_MYTYPE"
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Зависимость My от типа проекта (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Объект `My` предоставляет только те объекты, которые необходимы для конкретного типа проекта.  Например, объект `My.Forms` является доступным в приложении Windows Forms, но не доступен в консольном приложении.  В данном разделе описываются объекты `My`, доступные в различных типах проектов.  
  
## Объект My в приложениях Windows и веб\-узлах  
 Объект `My` предоставляет только объекты, которые полезны в текущем типе проекта; объекты, которые не применимы, подавляются.  Например, на следующем рисунке показана модель объекта `My` в проекте Windows Forms.  
  
 ![Форма My в приложение Windows Forms](../../../visual-basic/developing-apps/development-with-my/media/myinwinform.png "MyInWinForm")  
  
 В проекте веб\-узла `My` предоставляет объекты, существенные для веб\-разработчика \(например, объекты `My.Request` и `My.Response`\), скрывая неактуальные объекты \(такие как объект `My.Forms`\).  На следующем рисунке показана модель объекта `My` в проекте веб\-узла:  
  
 ![Форма My в веб&#45;приложении](../../../visual-basic/developing-apps/development-with-my/media/myinweb.png "MyInWeb")  
  
## Сведения о проекте  
 В следующей таблице показаны объекты `My`, включенные по умолчанию для восьми типов проектов: приложения Windows, библиотеки типов, консольного приложения, библиотек элементов управления Windows, библиотеки веб\-элементов управления, службы Windows, пустого проекта и веб\-узла.  
  
 Существуют три версии объекта `My.Application`, две версии объекта `My.Computer` и две версии объекта `My.User`; сведения об этих версиях приведены в сносках после таблицы.  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|Объект My|Приложение Windows|Библиотека классов|Консольное приложение|Библиотека элементов управления Windows|Библиотека веб\-элементов управления|Служба Windows|Пусто|Веб\-узел|  
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
  
 <sup>1</sup> Версия `My.Application` для Windows Forms.  Является производной от консольной версии \(см. примечание 3\). Дополнительно поддерживает взаимодействие с окнами приложения и предоставляет модель объекта Application [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 <sup>2</sup> Версия `My.Application` для библиотек.  Предоставляет базовую функциональность, необходимую приложению — элемента для записи в журнал и доступа к информации о приложении.  
  
 <sup>3</sup> Консольная версия `My.Application`.  Является производной от версии для библиотек \(см. примечание 2\). Содержит дополнительные элементы для доступа к аргументам командной строки приложения и сведения о развертывании ClickOnce.  
  
 <sup>4</sup> Версия `My.Computer` для Windows.  Является производной от серверной версии \(см. примечание 5\) и предоставляет доступ к полезным объектам на клиентском компьютере, таким как клавиатура, экран и мышь.  
  
 <sup>5</sup> Серверная версия `My.Computer`.  Предоставляет основные сведения о компьютере, такие как имя, доступ к часам и т. д.  
  
 <sup>6</sup> Версия `My.User` для Windows.  Этот объект связан с текущим удостоверением потока.  
  
 <sup>7</sup> Веб\-версия `My.User`.  Этот объект связан с удостоверением пользователя текущего HTTP\-запроса приложения.  
  
## См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.Logging.Log>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [\/define](../../../visual-basic/reference/command-line-compiler/define.md)   
 [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)   
 [Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)   
 [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)