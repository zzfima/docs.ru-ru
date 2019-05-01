---
title: Практическое руководство. Задание заголовка окна из страницы
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 55444de6c61107979307b94910ba944e7001cf9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054007"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a>Практическое руководство. Задание заголовка окна из страницы
В этом примере показано, как установить заголовок окна, в котором <xref:System.Windows.Controls.Page> размещается.  
  
## <a name="example"></a>Пример  
 Страница можно изменить заголовок окна, на котором размещается, задав <xref:System.Windows.Controls.Page.WindowTitle%2A> свойство, следующим образом:  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  Параметр <xref:System.Windows.Controls.Page.Title%2A> свойства страницы не приводит к изменению значения заголовка окна. Вместо этого <xref:System.Windows.Controls.Page.Title%2A> указывает имя записи страницы в журнале переходов.
