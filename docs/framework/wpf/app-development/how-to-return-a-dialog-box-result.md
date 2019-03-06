---
title: Практическое руководство. Возвращает результат диалогового окна
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: b574a5bbc08d947371837116915c2fc8c13ec81d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357772"
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="2c93c-102">Практическое руководство. Возвращает результат диалогового окна</span><span class="sxs-lookup"><span data-stu-id="2c93c-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="2c93c-103">В этом примере показано, как получить результат диалогового окна для окна, которое открывается путем вызова <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="2c93c-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c93c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="2c93c-104">Example</span></span>  
 <span data-ttu-id="2c93c-105">Прежде чем диалоговое окно закрывается, его <xref:System.Windows.Window.DialogResult%2A> свойство должно быть установлено с <xref:System.Nullable%601> <xref:System.Boolean> , указывающее, каким образом пользователь закрыл диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="2c93c-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="2c93c-106">Это значение возвращается по <xref:System.Windows.Window.ShowDialog%2A> коду клиента для определения способа закрытия диалогового окна и, следовательно, как обрабатывать результат.</span><span class="sxs-lookup"><span data-stu-id="2c93c-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c93c-107"><xref:System.Windows.Window.DialogResult%2A> можно устанавливать, только если окно было открыто, вызвав <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="2c93c-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="2c93c-108">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2c93c-108">.NET Framework Security</span></span>  
 <span data-ttu-id="2c93c-109">Вызов <xref:System.Windows.Window.ShowDialog%2A> требуется разрешение на использование все окна и события пользовательского ввода без ограничений.</span><span class="sxs-lookup"><span data-stu-id="2c93c-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
