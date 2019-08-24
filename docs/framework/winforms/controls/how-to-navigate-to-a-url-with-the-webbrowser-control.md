---
title: Практическое руководство. Переход по заданному URL с помощью элемента управления WebBrowser
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.Navigate
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- URLs [Windows Forms], navigating to
- WebBrowser control [Windows Forms], navigating to URLs
- examples [Windows Forms], WebBrowser control
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
ms.openlocfilehash: b6c1255fa17d91daaa73001fea04f26e73dba0ae
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015830"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a>Практическое руководство. Переход по заданному URL с помощью элемента управления WebBrowser
В следующем примере кода показано, как перемещаться <xref:System.Windows.Forms.WebBrowser> по элементу управления по определенному URL-адресу.

 Чтобы определить, когда новый документ полностью загружен, обработайте <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> событие. Демонстрацию этого события см. в разделе [как Печать с помощью элемента управления](how-to-print-with-a-webbrowser-control.md)WebBrowser.

## <a name="example"></a>Пример

```vb
Me.webBrowser1.Navigate("http://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("http://www.microsoft.com");
```

## <a name="compiling-the-code"></a>Компиляция кода
 Для этого примера требуются:

- элемент управления <xref:System.Windows.Forms.WebBrowser> с именем `webBrowser1`;

- ссылки на сборки `System` и `System.Windows.Forms`.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [Элемент управления WebBrowser](webbrowser-control-windows-forms.md)
- [Практическое руководство. Печать с помощью элемента управления WebBrowser](how-to-print-with-a-webbrowser-control.md)
