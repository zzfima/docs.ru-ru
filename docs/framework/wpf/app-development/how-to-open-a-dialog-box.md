---
title: Практическое руководство. Отображение диалогового окна
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
ms.openlocfilehash: 70ac31285dd22244b4bd6ad0d188d182eb6e6264
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084991"
---
# <a name="how-to-open-a-dialog-box"></a><span data-ttu-id="7a0a0-102">Практическое руководство. Отображение диалогового окна</span><span class="sxs-lookup"><span data-stu-id="7a0a0-102">How to: Open a Dialog Box</span></span>
<span data-ttu-id="7a0a0-103">В этом примере показано, как открыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="7a0a0-103">This example shows how to open a dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a0a0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="7a0a0-104">Example</span></span>  
 <span data-ttu-id="7a0a0-105">Диалоговое окно является окном, которое открывается путем создания экземпляра <xref:System.Windows.Window> и вызов <xref:System.Windows.Window.ShowDialog%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="7a0a0-105">A dialog box is a window that is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="7a0a0-106"><xref:System.Windows.Window.ShowDialog%2A> Открывает окно и не отвечала до новое диалоговое окно было закрыто.</span><span class="sxs-lookup"><span data-stu-id="7a0a0-106"><xref:System.Windows.Window.ShowDialog%2A> opens a window and doesn't return until the new dialog box has been closed.</span></span> <span data-ttu-id="7a0a0-107">Этот тип окна называется также *модального* окно и ограничивает ввод данных пользователем.</span><span class="sxs-lookup"><span data-stu-id="7a0a0-107">This type of window is also known as a *modal* window, and restricts user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="7a0a0-108">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7a0a0-108">.NET Framework Security</span></span>  
 <span data-ttu-id="7a0a0-109">Вызов <xref:System.Windows.Window.ShowDialog%2A> требуется разрешение на использование все окна и события пользовательского ввода без ограничений.</span><span class="sxs-lookup"><span data-stu-id="7a0a0-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a0a0-110">См. также</span><span class="sxs-lookup"><span data-stu-id="7a0a0-110">See also</span></span>

- [<span data-ttu-id="7a0a0-111">Возвращение результата диалогового окна</span><span class="sxs-lookup"><span data-stu-id="7a0a0-111">Return a Dialog Box Result</span></span>](how-to-return-a-dialog-box-result.md)
