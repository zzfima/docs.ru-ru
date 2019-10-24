---
title: Настройка доступа к объектам через My (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: bb3f8eb2e8b1cf5bce364fc4b3ce0587769bb5f9
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775215"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Настройка доступа к объектам через My (Visual Basic)

В этом разделе описывается, как можно контролировать, какие `My` объекты включены, установив константу условной компиляции `_MYTYPE` проекта. Интегрированная среда разработки Visual Studio (IDE) поддерживает `_MYTYPE` константу условной компиляции для проекта в синхронизации с типом проекта.  
  
## <a name="predefined-_mytype-values"></a>Предопределенные значения \_MYTYPE  

Чтобы задать константу условной компиляции `_MYTYPE`, необходимо использовать параметр компилятора `/define`. При указании собственного значения для `_MYTYPE` константе необходимо заключить строковое значение в последовательности обратной косой черты или кавычки (\\ "). Например, можно использовать:  
  
```console  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 В этой таблице показано, что в качестве константы условной компиляции `_MYTYPE` задано для нескольких типов проектов.  
  
|Тип проекта|\_MYTYPE значение|  
|------------------|--------------------|  
|Библиотека классов|Windows|  
|Консольное приложение|Консол|  
|Интернет|Интернет|  
|Библиотека веб-элементов управления|WebControl|  
|Приложение Windows|WindowsForms|  
|Приложение Windows, при запуске с настраиваемым `Sub Main`|"Виндовсформсвискустомсубмаин"|  
|Библиотека элементов управления Windows|Windows|  
|Служба Windows|Консол|  
|Empty|Указано|  
  
> [!NOTE]
> Все сравнения строк условной компиляции учитывают регистр, независимо от того, как задана инструкция `Option Compare`.  
  
## <a name="dependent-_my-compilation-constants"></a>Константы зависимых \_MY компиляции  

Константа условной компиляции `_MYTYPE`, в свою очередь, управляет значениями нескольких других констант компиляции `_MY`:  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|Консол|Консол|Windows|Не определено|Windows|true|  
|Настройки|Не определено|Не определено|Не определено|Не определено|Не определено|  
|Указано|Не определено|Не определено|Не определено|Не определено|Не определено|  
|Интернет|Не определено|Интернет|false|Интернет|false|  
|WebControl|Не определено|Интернет|false|Интернет|true|  
|"Windows" или ""|Windows|Windows|Не определено|Windows|true|  
|WindowsForms|WindowsForms|Windows|true|Windows|true|  
|"Виндовсформсвискустомсубмаин"|Консол|Windows|true|Windows|true|  
  
 По умолчанию неопределенные константы условной компиляции разрешаются в `FALSE`. При компиляции проекта можно указать значения для неопределенных констант, чтобы переопределить поведение по умолчанию.  
  
> [!NOTE]
> Если `_MYTYPE` имеет значение "Custom", проект содержит `My` пространство имен, но не содержит объектов. Однако при установке `_MYTYPE` в значение "Empty" компилятор не будет добавлять `My` пространство имен и его объекты.  
  
 В этой таблице описаны последствия предопределенных значений констант компиляции `_MY`.  
  
|Константа|Смысл|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Включает `My.Application`, если константа имеет значение "Console", "Windows" или "WindowsForms":<br /><br /> — Версия "Console" является производной от <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>. и имеет меньше элементов, чем версия Windows.<br />— Версия "Windows" является производной от <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>. и имеет меньше элементов, чем версия "WindowsForms".<br />— Версия "WindowsForms" `My.Application` является производной от <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Если константа `TARGET` определена как "winexe", то класс включает метод `Sub Main`.|  
|`_MYCOMPUTERTYPE`|Включает `My.Computer`, если константа имеет значение "Web" или "Windows":<br /><br /> — Версия "Web" является производной от <xref:Microsoft.VisualBasic.Devices.ServerComputer> и содержит меньше элементов, чем версия "Windows".<br />— Версия "Windows" `My.Computer` является производной от <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Включает `My.Forms`, если константа `TRUE`.|  
|`_MYUSERTYPE`|Включает `My.User`, если константа имеет значение "Web" или "Windows":<br /><br /> — Версия "Web" `My.User` связана с удостоверением пользователя текущего HTTP-запроса.<br />— Версия "Windows" `My.User` связана с текущим участником потока.|  
|`_MYWEBSERVICES`|Включает `My.WebServices`, если константа `TRUE`.|  
|`_MYTYPE`|Включает `My.Log`, `My.Request` и `My.Response`, если константа имеет значение "Web".|  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Зависимость My от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
- [Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)
- [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
