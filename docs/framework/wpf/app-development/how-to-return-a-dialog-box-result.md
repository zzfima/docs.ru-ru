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
# <a name="how-to-return-a-dialog-box-result"></a>Как: возвращает результат диалогового окна
В этом примере показано, как получить результат диалогового окна для окна, которое открывается вызовом <xref:System.Windows.Window.ShowDialog%2A>.  
  
## <a name="example"></a>Пример  
 Перед закрытием диалоговое окно, его <xref:System.Windows.Window.DialogResult%2A> свойство должно быть установлено с <xref:System.Nullable%601> <xref:System.Boolean> , указывающее, как пользователь закрыл диалоговое окно. Это значение возвращается по <xref:System.Windows.Window.ShowDialog%2A> коду клиента для определения способа закрытия диалогового окна и, следовательно, как для обработки результатов.  
  
> [!NOTE]
>  <xref:System.Windows.Window.DialogResult%2A> можно устанавливать, только если окно было открыто путем вызова <xref:System.Windows.Window.ShowDialog%2A>.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Вызов <xref:System.Windows.Window.ShowDialog%2A> требуется разрешение на использование все окна и события пользовательского ввода без ограничений.
