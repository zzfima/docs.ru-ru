---
title: Практическое руководство. Получение всех окон в приложении
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
ms.openlocfilehash: 34316f0c6f81b960a8e00131a30b9a237b9ca938
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947775"
---
# <a name="how-to-get-all-windows-in-an-application"></a>Практическое руководство. Получение всех окон в приложении
В этом примере показано, как получить все <xref:System.Windows.Window> объектов в приложении.  
  
## <a name="example"></a>Пример  
 Каждый экземпляр <xref:System.Windows.Window> объекта, является ли видимым или нет, автоматически добавляется в коллекцию ссылок на окно, управляется <xref:System.Windows.Application>и предоставлять их из <xref:System.Windows.Application.Windows%2A>.  
  
 Вы можете перечислить <xref:System.Windows.Application.Windows%2A> получить все экземпляры windows, используя следующий код:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
