---
title: "Как: открывает диалоговое окно"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d318f35f8f009f0f2c77210ca8b6b29bedfb7619
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-dialog-box"></a><span data-ttu-id="0c886-102">Как: открывает диалоговое окно</span><span class="sxs-lookup"><span data-stu-id="0c886-102">How to: Open a Dialog Box</span></span>
<span data-ttu-id="0c886-103">В этом примере показано, как открыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="0c886-103">This example shows how to open a dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c886-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0c886-104">Example</span></span>  
 <span data-ttu-id="0c886-105">Диалоговое окно является окном, которое открывается с помощью создания <xref:System.Windows.Window> и вызов <xref:System.Windows.Window.ShowDialog%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="0c886-105">A dialog box is a window that is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="0c886-106"><xref:System.Windows.Window.ShowDialog%2A>Открывает окно и не возвращает до новое диалоговое окно было закрыто.</span><span class="sxs-lookup"><span data-stu-id="0c886-106"><xref:System.Windows.Window.ShowDialog%2A> opens a window and doesn't return until the new dialog box has been closed.</span></span> <span data-ttu-id="0c886-107">Этот тип окна называется также *модального* окно и ограничивает ввод данных пользователем.</span><span class="sxs-lookup"><span data-stu-id="0c886-107">This type of window is also known as a *modal* window, and restricts user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="0c886-108">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0c886-108">.NET Framework Security</span></span>  
 <span data-ttu-id="0c886-109">Вызов <xref:System.Windows.Window.ShowDialog%2A> требуется разрешение на использование все окна и события пользовательского ввода без ограничений.</span><span class="sxs-lookup"><span data-stu-id="0c886-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c886-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0c886-110">See Also</span></span>  
 [<span data-ttu-id="0c886-111">Возвращение результата диалогового окна</span><span class="sxs-lookup"><span data-stu-id="0c886-111">Return a Dialog Box Result</span></span>](../../../../docs/framework/wpf/app-development/how-to-return-a-dialog-box-result.md)
