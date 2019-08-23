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
# <a name="how-to-return-a-dialog-box-result"></a>Практическое руководство. Возвращение результата диалогового окна
В этом примере показано, как получить результат диалогового окна, открытого с помощью вызова метода <xref:System.Windows.Window.ShowDialog%2A>.  
  
## <a name="example"></a>Пример  
 Перед закрытием диалогового окна его <xref:System.Windows.Window.DialogResult%2A> свойству должно быть присвоено <xref:System.Nullable%601> <xref:System.Boolean> значение, которое указывает, как пользователь закрыл диалоговое окно. Это значение возвращается, <xref:System.Windows.Window.ShowDialog%2A> чтобы разрешить коду клиента определить, как было закрыто диалоговое окно, и, следовательно, как обработать результат.  
  
> [!NOTE]
> <xref:System.Windows.Window.DialogResult%2A>может быть задан только в том случае, если окно было <xref:System.Windows.Window.ShowDialog%2A>открыто путем вызова.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Для <xref:System.Windows.Window.ShowDialog%2A> вызова требуется разрешение на использование всех окон и событий ввода данных пользователем без ограничений.
