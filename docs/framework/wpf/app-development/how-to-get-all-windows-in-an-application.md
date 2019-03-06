---
title: Практическое руководство. Получение всех Windows в приложении
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
ms.openlocfilehash: 34316f0c6f81b960a8e00131a30b9a237b9ca938
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378843"
---
# <a name="how-to-get-all-windows-in-an-application"></a><span data-ttu-id="18e8b-102">Практическое руководство. Получение всех Windows в приложении</span><span class="sxs-lookup"><span data-stu-id="18e8b-102">How to: Get all Windows in an Application</span></span>
<span data-ttu-id="18e8b-103">В этом примере показано, как получить все <xref:System.Windows.Window> объектов в приложении.</span><span class="sxs-lookup"><span data-stu-id="18e8b-103">This example shows how to get all <xref:System.Windows.Window> objects in an application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18e8b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="18e8b-104">Example</span></span>  
 <span data-ttu-id="18e8b-105">Каждый экземпляр <xref:System.Windows.Window> объекта, является ли видимым или нет, автоматически добавляется в коллекцию ссылок на окно, управляется <xref:System.Windows.Application>и предоставлять их из <xref:System.Windows.Application.Windows%2A>.</span><span class="sxs-lookup"><span data-stu-id="18e8b-105">Every instantiated <xref:System.Windows.Window> object, whether visible or not, is automatically added to a collection of window references that is managed by <xref:System.Windows.Application>, and exposed from <xref:System.Windows.Application.Windows%2A>.</span></span>  
  
 <span data-ttu-id="18e8b-106">Вы можете перечислить <xref:System.Windows.Application.Windows%2A> получить все экземпляры windows, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="18e8b-106">You can enumerate <xref:System.Windows.Application.Windows%2A> to get all instantiated windows using the following code:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
