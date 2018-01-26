---
title: "Как: задание заголовка окна со страницы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 11f33eede479e090a78bffe841d7998e03eab6c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a>Как: задание заголовка окна со страницы
В этом примере показано, как задать заголовок окна, в котором <xref:System.Windows.Controls.Page> размещается.  
  
## <a name="example"></a>Пример  
 Страница можно изменить заголовок окна, содержащего его, установив <xref:System.Windows.Controls.Page.WindowTitle%2A> свойства следующим образом:  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  Параметр <xref:System.Windows.Controls.Page.Title%2A> свойства страницы не изменяет значение заголовка окна. Вместо этого <xref:System.Windows.Controls.Page.Title%2A> указывает имя записи страницы в журнале навигации.
