---
title: Практическое руководство. Возвращение результата диалогового окна
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: 5e3670006762bcd09634b29314ecf2d05b1a44da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968232"
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="42607-102">Практическое руководство. Возвращение результата диалогового окна</span><span class="sxs-lookup"><span data-stu-id="42607-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="42607-103">В этом примере показано, как получить результат диалогового окна, открытого с помощью вызова метода <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="42607-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42607-104">Пример</span><span class="sxs-lookup"><span data-stu-id="42607-104">Example</span></span>  
 <span data-ttu-id="42607-105">Перед закрытием диалогового окна его <xref:System.Windows.Window.DialogResult%2A> свойству должно быть присвоено <xref:System.Nullable%601> <xref:System.Boolean> значение, которое указывает, как пользователь закрыл диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="42607-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="42607-106">Это значение возвращается, <xref:System.Windows.Window.ShowDialog%2A> чтобы разрешить коду клиента определить, как было закрыто диалоговое окно, и, следовательно, как обработать результат.</span><span class="sxs-lookup"><span data-stu-id="42607-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42607-107"><xref:System.Windows.Window.DialogResult%2A>может быть задан только в том случае, если окно было <xref:System.Windows.Window.ShowDialog%2A>открыто путем вызова.</span><span class="sxs-lookup"><span data-stu-id="42607-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="42607-108">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="42607-108">.NET Framework Security</span></span>  
 <span data-ttu-id="42607-109">Для <xref:System.Windows.Window.ShowDialog%2A> вызова требуется разрешение на использование всех окон и событий ввода данных пользователем без ограничений.</span><span class="sxs-lookup"><span data-stu-id="42607-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
