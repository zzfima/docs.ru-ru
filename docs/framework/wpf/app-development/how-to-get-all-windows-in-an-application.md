---
title: 'Как: получение всех окон в приложении'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
ms.openlocfilehash: 476905899f5f7d573a16ba876c72f28ea34bbf9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-all-windows-in-an-application"></a><span data-ttu-id="f24a1-102">Как: получение всех окон в приложении</span><span class="sxs-lookup"><span data-stu-id="f24a1-102">How to: Get all Windows in an Application</span></span>
<span data-ttu-id="f24a1-103">В этом примере показано, как получить все <xref:System.Windows.Window> объектов в приложении.</span><span class="sxs-lookup"><span data-stu-id="f24a1-103">This example shows how to get all <xref:System.Windows.Window> objects in an application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f24a1-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f24a1-104">Example</span></span>  
 <span data-ttu-id="f24a1-105">Каждый экземпляр <xref:System.Windows.Window> объекта, является ли видимым или нет, автоматически добавляется в коллекцию ссылок на окно, управляется <xref:System.Windows.Application>и предоставляемую из <xref:System.Windows.Application.Windows%2A>.</span><span class="sxs-lookup"><span data-stu-id="f24a1-105">Every instantiated <xref:System.Windows.Window> object, whether visible or not, is automatically added to a collection of window references that is managed by <xref:System.Windows.Application>, and exposed from <xref:System.Windows.Application.Windows%2A>.</span></span>  
  
 <span data-ttu-id="f24a1-106">Можно перечислить <xref:System.Windows.Application.Windows%2A> получить все экземпляры окна, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="f24a1-106">You can enumerate <xref:System.Windows.Application.Windows%2A> to get all instantiated windows using the following code:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
