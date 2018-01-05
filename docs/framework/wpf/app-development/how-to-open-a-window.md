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
ms.workload: dotnet
ms.openlocfilehash: c6f3efda8257d9f7ed843438b0e9fb42e13de2c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-open-a-window"></a><span data-ttu-id="bf166-102">Как: Открытие окна</span><span class="sxs-lookup"><span data-stu-id="bf166-102">How to: Open a Window</span></span>
<span data-ttu-id="bf166-103">В этом примере показано, как открыть окно.</span><span class="sxs-lookup"><span data-stu-id="bf166-103">This example shows how to open a window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf166-104">Пример</span><span class="sxs-lookup"><span data-stu-id="bf166-104">Example</span></span>  
 <span data-ttu-id="bf166-105">Открывается окно путем создания экземпляра <xref:System.Windows.Window> и вызов <xref:System.Windows.Window.Show%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="bf166-105">A window is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.Show%2A> method.</span></span> <span data-ttu-id="bf166-106"><xref:System.Windows.Window.Show%2A>Открывает окно и немедленно возвращается, не дожидаясь закрытия нового окна.</span><span class="sxs-lookup"><span data-stu-id="bf166-106"><xref:System.Windows.Window.Show%2A> opens a window and returns immediately without waiting for the new window to close.</span></span> <span data-ttu-id="bf166-107">Этот тип окна называется также *немодальное* окна и не ограничивает ввод данных пользователем.</span><span class="sxs-lookup"><span data-stu-id="bf166-107">This type of window is also known as a *modeless* window, and doesn't restrict user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="bf166-108">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bf166-108">.NET Framework Security</span></span>  
 <span data-ttu-id="bf166-109">При создании экземпляра <xref:System.Windows.Window> требуется разрешение на вызов небезопасных собственных методов (см. <xref:System.Windows.Window.%23ctor%2A>).</span><span class="sxs-lookup"><span data-stu-id="bf166-109">Instantiating <xref:System.Windows.Window> requires permission to call unsafe native methods (see <xref:System.Windows.Window.%23ctor%2A>).</span></span>
