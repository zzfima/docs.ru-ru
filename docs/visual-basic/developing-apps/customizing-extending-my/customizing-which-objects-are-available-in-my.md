---
title: "Настройка доступа к объектам, доступные через My (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My namespace, customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 6791398270e4348adf356eb36a385bfbefde873c
ms.lasthandoff: 03/13/2017

---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Настройка доступа к объектам через My (Visual Basic)
В этом разделе описывается, как можно управлять `My` объекты включены, задав проекта `_MYTYPE` константы условной компиляции. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Интегрированной среды разработки (IDE) отслеживает `_MYTYPE` константы условной компиляции проекта в соответствии с типом проекта.  
  
## <a name="predefined-mytype-values"></a>Предопределенные значения _MYTYPE  
 Необходимо использовать `/define` параметр компилятора, чтобы задать `_MYTYPE` константы условной компиляции. При указании значения для `_MYTYPE` константой, необходимо заключить строковое значение в обратная косая черта и кавычка (\\») последовательности. Например можно использовать:  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 В этой таблице показано, что `_MYTYPE` имеет значение константы условной компиляции для нескольких типов проектов.  
  
|Тип проекта|Значение _MYTYPE|  
|------------------|--------------------|  
|Библиотека классов|«Windows»|  
|Консольное приложение|«Консоль»|  
|Интернет|«Web»|  
|Библиотека веб-элементов управления|«WebControl»|  
|Приложение Windows|«WindowsForms»|  
|Приложение Windows, при запуске с пользовательской процедурой`Sub Main`|«WindowsFormsWithCustomSubMain»|  
|Библиотека элементов управления Windows|«Windows»|  
|Служба Windows|«Консоль»|  
|Empty|«Empty»|  
  
> [!NOTE]
>  Условной компиляции все строковые сравнения с учетом регистра, независимо от того, как `Option Compare` инструкции set.  
  
## <a name="dependent-my-compilation-constants"></a>Зависимые константы компиляции _MY  
 `_MYTYPE` Константы условной компиляции, в свою очередь, управляет значениями некоторых других `_MY` константы компиляции:  
  
|_MYTYPE|_MYAPPLICATIONTYPE|_MYCOMPUTERTYPE|_MYFORMS|_MYUSERTYPE|_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|«Консоль»|«Консоль»|«Windows»|Не определено|«Windows»|TRUE|  
|«Custom»|Не определено|Не определено|Не определено|Не определено|Не определено|  
|«Empty»|Не определено|Не определено|Не определено|Не определено|Не определено|  
|«Web»|Не определено|«Web»|FALSE|«Web»|FALSE|  
|«WebControl»|Не определено|«Web»|FALSE|«Web»|TRUE|  
|«Windows» или «»|«Windows»|«Windows»|Не определено|«Windows»|TRUE|  
|«WindowsForms»|«WindowsForms»|«Windows»|TRUE|«Windows»|TRUE|  
|«WindowsFormsWithCustomSubMain»|«Консоль»|«Windows»|TRUE|«Windows»|TRUE|  
  
 По умолчанию не определено константы условной компиляции решения для `FALSE`. Можно указать значения для неопределенных констант при компиляции проекта, чтобы переопределить поведение по умолчанию.  
  
> [!NOTE]
>  Когда `_MYTYPE` установлено значение «Custom», проект содержит `My` пространства имен, но не содержит объектов. Однако задание `_MYTYPE` в «Empty» указывает компилятору добавление `My` пространства имен и ее объектов.  
  
 В этой таблице описаны последствия использования предопределенных значений `_MY` константы компиляции.  
  
|Константа|Значение|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Позволяет `My.Application`, если константа «Консоли «Windows» или «WindowsForms»:<br /><br /> -Версия «Консоль» является производным от <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>.</xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> и содержит меньше элементов, чем версия «Windows».<br />-Версию «Windows» является производным от <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>и имеет меньше элементов, чем версия «WindowsForms».</xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase><br />Версия «WindowsForms» `My.Application` является производным от <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Если `TARGET` определена константа «winexe», то класс включает `Sub Main` метод.|  
|`_MYCOMPUTERTYPE`|Позволяет `My.Computer`, если значение константы равно «Веб» или «Windows»:<br /><br /> -Версия «Веб» является производным от <xref:Microsoft.VisualBasic.Devices.ServerComputer>, и содержит меньше элементов, чем версия «Windows».</xref:Microsoft.VisualBasic.Devices.ServerComputer><br />-«Windows» версии `My.Computer` является производным от <xref:Microsoft.VisualBasic.Devices.Computer>.</xref:Microsoft.VisualBasic.Devices.Computer>|  
|`_MYFORMS`|Позволяет `My.Forms`, если значение константы равно `TRUE`.|  
|`_MYUSERTYPE`|Позволяет `My.User`, если значение константы равно «Веб» или «Windows»:<br /><br /> -«Веб» версию `My.User` связан с удостоверением пользователя текущего HTTP-запроса.<br />-«Windows» версии `My.User` связан с текущего участника потока.|  
|`_MYWEBSERVICES`|Позволяет `My.WebServices`, если значение константы равно `TRUE`.|  
|`_MYTYPE`|Позволяет `My.Log`, `My.Request`, и `My.Response`, если константа «Web».|  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer></xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.Logging.Log></xref:Microsoft.VisualBasic.Logging.Log>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User></xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [Как Мой зависит от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)   
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)   
 [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)   
 [Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)   
 [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
