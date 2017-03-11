---
title: "Настройка доступа к объектам через My (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My - пространство имен"
  - "My - пространство имен, настройка"
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Настройка доступа к объектам через My (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

В этом разделе описываются способы управления включением объектов `My` путем задания константы условной компиляции проекта `_MYTYPE`.  Интегрированная среда разработки [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] выбирает константу условной компиляции `_MYTYPE` для проекта в соответствии с типом проекта.  
  
## Предопределенные значения \_MYTYPE  
 Для задания константы условной компиляции `_MYTYPE` необходимо использовать параметр компилятора `/define`.  При указании пользовательского значения для константы `_MYTYPE` необходимо заключить строковое значение последовательностями "обратная косая черта \+ двойная кавычка" \(\\"\).  Например, можно использовать:  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 В следующей таблице показаны различные значения константы условной компиляции `_MYTYPE` для нескольких типов проектов.  
  
|Тип проекта|Значение \_MYTYPE|  
|-----------------|-----------------------|  
|Библиотека классов|"Windows"|  
|Консольное приложение|"Console"|  
|Веб|"Web"|  
|Библиотека веб\-элементов управления|"WebControl"|  
|Приложение Windows|"WindowsForms"|  
|Приложение Windows, при запуске с пользовательской процедурой `Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Библиотека элементов управления Windows|"Windows"|  
|Служба Windows|"Console"|  
|Пусто|"Empty"|  
  
> [!NOTE]
>  При условной компиляции все строковые сравнения проводятся с учетом регистра вне зависимости от значения параметра `Option Compare`.  
  
## Зависимые константы компиляции \_MY  
 В свою очередь, константа условной компиляции `_MYTYPE` управляет значениями некоторых других констант условной компиляции `_MY`.  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Console"|"Console"|"Windows"|Не определено|"Windows"|TRUE|  
|"Custom"|Не определено|Не определено|Не определено|Не определено|Не определено|  
|"Empty"|Не определено|Не определено|Не определено|Не определено|Не определено|  
|"Web"|Не определено|"Web"|FALSE|"Web"|FALSE|  
|"WebControl"|Не определено|"Web"|FALSE|"Web"|TRUE|  
|"Windows" или ""|"Windows"|"Windows"|Не определено|"Windows"|TRUE|  
|"WindowsForms"|"WindowsForms"|"Windows"|TRUE|"Windows"|TRUE|  
|"WindowsFormsWithCustomSubMain"|"Console"|"Windows"|TRUE|"Windows"|TRUE|  
  
 По умолчанию неопределенные константы условной компиляция имеют значение `FALSE`.  Можно указать значения для неопределенных констант при компиляции проекта, переопределив значения по умолчанию.  
  
> [!NOTE]
>  Если значение константы `_MYTYPE` равно "Custom", проект содержит пространство имен `My`, но он не содержит объектов.  Однако, если константе `_MYTYPE` присвоено значение "Empty", компилятор не будет добавлять пространство имен `My` и его объекты.  
  
 В этой таблице описаны последствия использования предопределенных значений констант компиляции `_MY`.  
  
|Константа|Значение|  
|---------------|--------------|  
|`_MYAPPLICATIONTYPE`|Включает объект `My.Application`, если значение константы равно "Console", "Windows" или "WindowsForms".<br /><br /> -   Версия "Console" наследуется от объекта <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>.  и имеет меньше членов, чем версия "Windows".<br />-   Версия "Console" является производной от <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> и имеет меньшее число элементов, чем версия "WindowsForms".<br />-   Версия "WindowsForms" объекта `My.Application` является производной от <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>.  Если константа `TARGET` равна "winexe", то класс содержит метод `Sub Main`.|  
|`_MYCOMPUTERTYPE`|Включает объект `My.Computer`, если значение константы равно "Web" или "Windows".<br /><br /> -   Версия "Web" является производной от <xref:Microsoft.VisualBasic.Devices.ServerComputer> и имеет меньшее число элементов, чем версия "Windows".<br />-   Версия "Windows"объекта `My.Computer` является производной от <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Включает объект `My.Forms`, если значение константы равно `TRUE`.|  
|`_MYUSERTYPE`|Включает объект `My.User`, если значение константы равно "Web" или "Windows".<br /><br /> -   Версия "Web" объекта `My.User` связана с идентификатором пользователя текущего HTTP\-запроса.<br />-   Версия "Windows" объекта `My.User` связана с текущим участником потока.|  
|`_MYWEBSERVICES`|Включает объект `My.WebServices`, если значение константы равно `TRUE`.|  
|`_MYTYPE`|Включает объекты `My.Log`, `My.Request` и `My.Response`, если значение константы равно "Web".|  
  
## См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.Logging.Log>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [Зависимость My от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)   
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [\/define](../../../visual-basic/reference/command-line-compiler/define.md)   
 [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)   
 [Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)   
 [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)