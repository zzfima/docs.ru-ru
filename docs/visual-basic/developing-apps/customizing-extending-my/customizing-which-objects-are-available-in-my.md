---
title: Настройка доступа к объектам через My (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: caddad463f7c525c8b715d70f49bf8bebcc7cfbd
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701261"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Настройка доступа к объектам через My (Visual Basic)

В этом разделе описывается, как можно контролировать, какие объекты `My` включены, настроив константу условной компиляции `_MYTYPE` проекта. Интегрированная среда разработки Visual Studio (IDE) сохраняет константу условной компиляции `_MYTYPE` для проекта в синхронизации с типом проекта.  
  
## <a name="predefined-_mytype-values"></a>Предопределенные значения \_MYTYPE  

Для установки константы условной компиляции `_MYTYPE` необходимо использовать параметр компилятора `/define`. При указании собственного значения константы `_MYTYPE` необходимо заключить строковое значение в последовательности обратной косой черты или кавычки (\\ "). Например, можно использовать:  
  
```console  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 В этой таблице показано, что константа условной компиляции `_MYTYPE` задана для нескольких типов проектов.  
  
|Тип проекта|значение \_MYTYPE|  
|------------------|--------------------|  
|Библиотека классов|Windows|  
|Консольное приложение|Консол|  
|Интернет|Интернет|  
|Библиотека веб-элементов управления|WebControl|  
|Приложение Windows|WindowsForms|  
|Приложение Windows, при запуске с настраиваемой `Sub Main`|"Виндовсформсвискустомсубмаин"|  
|Библиотека элементов управления Windows|Windows|  
|Служба Windows|Консол|  
|Empty|Указано|  
  
> [!NOTE]
> Все сравнения строк условной компиляции учитывают регистр, независимо от того, как задана инструкция `Option Compare`.  
  
## <a name="dependent-_my-compilation-constants"></a>Зависимые @no__t-константы компиляции 0MY  

Константа условной компиляции `_MYTYPE`, в свою очередь, управляет значениями нескольких других констант компиляции `_MY`:  
  
|@NO__T 0MYTYPE|@NO__T 0MYAPPLICATIONTYPE|@NO__T 0MYCOMPUTERTYPE|@NO__T 0MYFORMS|@NO__T 0MYUSERTYPE|@NO__T 0MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|Консол|Консол|Windows|Не определено|Windows|TRUE|  
|Настройки|Не определено|Не определено|Не определено|Не определено|Не определено|  
|Указано|Не определено|Не определено|Не определено|Не определено|Не определено|  
|Интернет|Не определено|Интернет|FALSE|Интернет|FALSE|  
|WebControl|Не определено|Интернет|FALSE|Интернет|TRUE|  
|"Windows" или ""|Windows|Windows|Не определено|Windows|TRUE|  
|WindowsForms|WindowsForms|Windows|TRUE|Windows|TRUE|  
|"Виндовсформсвискустомсубмаин"|Консол|Windows|TRUE|Windows|TRUE|  
  
 По умолчанию неопределенные константы условной компиляции разрешаются в `FALSE`. При компиляции проекта можно указать значения для неопределенных констант, чтобы переопределить поведение по умолчанию.  
  
> [!NOTE]
> Если `_MYTYPE` имеет значение "Custom", проект содержит пространство имен `My`, но не содержит объектов. Однако установка `_MYTYPE` в значение "Empty" не позволяет компилятору добавлять пространство имен `My` и его объекты.  
  
 В этой таблице описаны последствия предопределенных значений констант компиляции `_MY`.  
  
|Константа|Значение|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Включает `My.Application`, если константа имеет значение "Console", "Windows" или "WindowsForms":<br /><br /> — Версия "Console" является производной от <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>. и имеет меньше элементов, чем версия Windows.<br />— Версия "Windows" является производной от @no__t -0. и имеет меньше элементов, чем версия "WindowsForms".<br />— Версия "WindowsForms" `My.Application` является производной от <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Если константа `TARGET` определена как "winexe", то класс включает метод `Sub Main`.|  
|`_MYCOMPUTERTYPE`|Включает `My.Computer`, если константа имеет значение "Web" или "Windows":<br /><br /> — Версия "Web" является производной от <xref:Microsoft.VisualBasic.Devices.ServerComputer> и содержит меньше элементов, чем версия "Windows".<br />— Версия "Windows" `My.Computer` является производной от <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Включает `My.Forms`, если константа имеет значение `TRUE`.|  
|`_MYUSERTYPE`|Включает `My.User`, если константа имеет значение "Web" или "Windows":<br /><br /> — Версия "Web" `My.User` связана с удостоверением пользователя текущего HTTP-запроса.<br />— Версия "Windows" `My.User` связана с текущим участником потока.|  
|`_MYWEBSERVICES`|Включает `My.WebServices`, если константа имеет значение `TRUE`.|  
|`_MYTYPE`|Включает `My.Log`, `My.Request` и `My.Response`, если константа имеет значение "Web".|  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Зависимость My от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
- [Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)
- [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
