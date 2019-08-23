---
title: Практическое руководство. Задание заголовка окна из страницы
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 0f618af89965822b0df96a264997dabd9cae7608
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940788"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a>Практическое руководство. Задание заголовка окна из страницы
В этом примере показано, как задать заголовок окна, в котором <xref:System.Windows.Controls.Page> размещается.  
  
## <a name="example"></a>Пример  
 Страница может изменить заголовок окна, в котором он размещается, задав <xref:System.Windows.Controls.Page.WindowTitle%2A> свойство следующим образом:  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
> <xref:System.Windows.Controls.Page.Title%2A> Установка свойства страницы не изменяет значение заголовка окна. Вместо этого <xref:System.Windows.Controls.Page.Title%2A> указывает имя записи страницы в журнале навигации.
