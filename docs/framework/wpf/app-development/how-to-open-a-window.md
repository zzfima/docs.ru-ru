---
title: "Как: Открытие окна"
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
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6eec13ec1bac864376fcdf5417cc4be68f16dd46
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-window"></a>Как: Открытие окна
В этом примере показано, как открыть окно.  
  
## <a name="example"></a>Пример  
 Открывается окно путем создания экземпляра <xref:System.Windows.Window> и вызов <xref:System.Windows.Window.Show%2A> метод. <xref:System.Windows.Window.Show%2A>Открывает окно и немедленно возвращается, не дожидаясь закрытия нового окна. Этот тип окна называется также *немодальное* окна и не ограничивает ввод данных пользователем.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 При создании экземпляра <xref:System.Windows.Window> требуется разрешение на вызов небезопасных собственных методов (см. <xref:System.Windows.Window.%23ctor%2A>).
