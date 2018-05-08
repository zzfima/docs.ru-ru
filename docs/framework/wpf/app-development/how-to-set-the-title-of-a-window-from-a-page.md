---
title: 'Как: задание заголовка окна со страницы'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: e69812b59783717b7b9c832d4e8ab01ab42827c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a>Как: задание заголовка окна со страницы
В этом примере показано, как задать заголовок окна, в котором <xref:System.Windows.Controls.Page> размещается.  
  
## <a name="example"></a>Пример  
 Страница можно изменить заголовок окна, содержащего его, установив <xref:System.Windows.Controls.Page.WindowTitle%2A> свойства следующим образом:  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  Параметр <xref:System.Windows.Controls.Page.Title%2A> свойства страницы не изменяет значение заголовка окна. Вместо этого <xref:System.Windows.Controls.Page.Title%2A> указывает имя записи страницы в журнале навигации.
