---
title: Настройка доступа к объектам через My (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: c0b47521c6a62071466ae4193cd8553bdfb3dcde
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58890375"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Настройка доступа к объектам через My (Visual Basic)

В этом разделе описывается, как можно выбирать, какие `My` объекты включены, задав проекта `_MYTYPE` константы условной компиляции. Интегрированная среда разработки (IDE) Visual Studio сохраняет `_MYTYPE` константа условной компиляции для проекта в соответствии с типом проекта.  
  
## <a name="predefined-mytype-values"></a>Предопределенные \_MYTYPE значения  

Необходимо использовать `/define` параметр компилятора, чтобы задать `_MYTYPE` константы условной компиляции. При указании значения для `_MYTYPE` константы, необходимо заключить строковое значение в обратная косая черта и кавычка (\\«) последовательности. Например можно использовать:  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 В этой таблице показано, что `_MYTYPE` имеет значение константы условной компиляции для нескольких типов проектов.  
  
|Тип проекта|\_Значение MYTYPE|  
|------------------|--------------------|  
|Библиотека классов|«Windows»|  
|Консольное приложение|«Консоль»|  
|Интернет|«Web»|  
|Web Control Library|«WebControl»|  
|Приложение Windows|«WindowsForms»|  
|При запуске с помощью пользовательского приложения Windows `Sub Main`|«WindowsFormsWithCustomSubMain»|  
|Библиотека элементов управления Windows|«Windows»|  
|Служба Windows|«Консоль»|  
|Empty|«Empty»|  
  
> [!NOTE]
> Все строки условной компиляции при сравнении учитывается регистр, независимо от способа `Option Compare` инструкции set.  
  
## <a name="dependent-my-compilation-constants"></a>Зависимые \_МОЕЙ константы компиляции  

`_MYTYPE` Константы условной компиляции, в свою очередь, управляет значениями из многих других `_MY` константы компиляции:  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|«Консоль»|«Консоль»|«Windows»|Не определено|«Windows»|true|  
|«Custom»|Не определено|Не определено|Не определено|Не определено|Не определено|  
|«Empty»|Не определено|Не определено|Не определено|Не определено|Не определено|  
|«Web»|Не определено|«Web»|false|«Web»|false|  
|«WebControl»|Не определено|«Web»|false|«Web»|true|  
|«Windows» или «»|«Windows»|«Windows»|Не определено|«Windows»|true|  
|«WindowsForms»|«WindowsForms»|«Windows»|true|«Windows»|true|  
|«WindowsFormsWithCustomSubMain»|«Консоль»|«Windows»|true|«Windows»|true|  
  
 По умолчанию сопоставляется неопределенный константы условной компиляции `FALSE`. Можно указать значения для неопределенных констант при компиляции проекта, чтобы переопределить поведение по умолчанию.  
  
> [!NOTE]
> Когда `_MYTYPE` устанавливается на «Пользовательский», проект содержит `My` пространства имен, но он не содержит объектов. Однако можно присвоить `_MYTYPE` для «Empty» запрещает компилятору добавление `My` пространства имен и ее объектов.  
  
 Эта таблица описывает последствия предопределенных значений `_MY` константы компиляции.  
  
|Константа|Значение|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Позволяет `My.Application`, если константа является «Console» Windows,» или «WindowsForms»:<br /><br /> -Версию «Консоль» является производным от <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>. и имеет меньше элементов, чем версия «Windows».<br />Версия «Windows» является производным от <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>и имеет меньше элементов, чем версия «WindowsForms».<br />— «WindowsForms» версия `My.Application` является производным от <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Если `TARGET` определена константа «winexe», а затем класс включает `Sub Main` метод.|  
|`_MYCOMPUTERTYPE`|Позволяет `My.Computer`, если константа является «Веб» или «Windows»:<br /><br /> -Версию «Web» является производным от <xref:Microsoft.VisualBasic.Devices.ServerComputer>, и содержит меньше элементов, чем версия «Windows».<br />— «Windows» версия `My.Computer` является производным от <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Позволяет `My.Forms`, если константа находится `TRUE`.|  
|`_MYUSERTYPE`|Позволяет `My.User`, если константа является «Веб» или «Windows»:<br /><br /> — «Web» версия `My.User` связана с удостоверением пользователя текущего HTTP-запроса.<br />— «Windows» версия `My.User` связан с текущего участника потока.|  
|`_MYWEBSERVICES`|Позволяет `My.WebServices`, если константа находится `TRUE`.|  
|`_MYTYPE`|Позволяет `My.Log`, `My.Request`, и `My.Response`, если константа является «Web».|  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Зависимость My от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
- [Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)
- [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
