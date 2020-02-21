---
title: Добавление возможностей веб-браузера в приложение
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WebBrowser control [Windows Forms], adding Web browser capabilities to your application
- WebBrowser control [Windows Forms], examples
- Web browsers [.NET Framework], adding to Windows Forms
- examples [Windows Forms], WebBrowser control
- Windows Forms, adding Web browser functionality
ms.assetid: 3871f072-b57a-435b-9976-e5da28df04a7
ms.openlocfilehash: 7cb789121f4aa9a1e7cef54f992d0697ce6dfc62
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543577"
---
# <a name="how-to-add-web-browser-capabilities-to-a-windows-forms-application"></a>Добавление возможностей веб-браузера в приложение Windows Forms

Элемент управления <xref:System.Windows.Forms.WebBrowser> позволяет добавить в приложение функциональность веб-браузера. По умолчанию он работает как веб-браузер. После загрузки начального URL-адреса путем установки свойства <xref:System.Windows.Forms.WebBrowser.Url%2A> можно переходить по гиперссылкам, а также совершать переход вперед и назад по истории навигации с помощью сочетаний клавиш. Дополнительные функциональные возможности браузера по умолчанию доступны в контекстном меню, появляющемся при щелчке правой кнопки мыши. Вы также можете открывать новые документы, сбрасывая их в элемент управления. Кроме того, элемент управления <xref:System.Windows.Forms.WebBrowser> имеет несколько свойств, методов и событий, которые можно использовать для реализации возможностей пользовательского интерфейса, аналогичных имеющимся в Internet Explorer.

В примере кода ниже реализуются адресная строка, стандартные кнопки браузера, меню **Файл**, строка состояния и строка заголовка, в которой содержится заголовок текущей страницы.

## <a name="example"></a>Пример

[!code-cpp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.WebBrowser#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]
  
## <a name="compile-the-code"></a>Компиляция кода

Для этого примера требуются:

- ссылки на сборки `System`, `System.Drawing` и `System.Windows.Forms`.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.WebBrowser>
- [Элемент управления WebBrowser](webbrowser-control-windows-forms.md)
