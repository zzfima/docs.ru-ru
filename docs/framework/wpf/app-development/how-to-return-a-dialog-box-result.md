---
title: 'Как: возвращает результат диалогового окна'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: 8f754577a355a58060238bbbb487c36aea14658c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545591"
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="dc5ad-102">Как: возвращает результат диалогового окна</span><span class="sxs-lookup"><span data-stu-id="dc5ad-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="dc5ad-103">В этом примере показано, как получить результат диалогового окна для окна, которое открывается вызовом <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc5ad-104">Пример</span><span class="sxs-lookup"><span data-stu-id="dc5ad-104">Example</span></span>  
 <span data-ttu-id="dc5ad-105">Перед закрытием диалоговое окно, его <xref:System.Windows.Window.DialogResult%2A> свойство должно быть установлено с <xref:System.Nullable%601> <xref:System.Boolean> , указывающее, как пользователь закрыл диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="dc5ad-106">Это значение возвращается по <xref:System.Windows.Window.ShowDialog%2A> коду клиента для определения способа закрытия диалогового окна и, следовательно, как для обработки результатов.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc5ad-107"><xref:System.Windows.Window.DialogResult%2A> можно устанавливать, только если окно было открыто путем вызова <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="dc5ad-108">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc5ad-108">.NET Framework Security</span></span>  
 <span data-ttu-id="dc5ad-109">Вызов <xref:System.Windows.Window.ShowDialog%2A> требуется разрешение на использование все окна и события пользовательского ввода без ограничений.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
