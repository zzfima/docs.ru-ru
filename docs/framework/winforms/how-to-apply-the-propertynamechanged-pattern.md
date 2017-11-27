---
title: "Практическое руководство. Применение шаблона PropertyNameChanged"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4f53dd2fdaa622e022f49c153b6dbc83030ae791
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="2d6d3-102">Практическое руководство. Применение шаблона PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="2d6d3-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="2d6d3-103">В следующем примере кода демонстрируется применение *PropertyName*шаблон Changed к пользовательскому элементу управления.</span><span class="sxs-lookup"><span data-stu-id="2d6d3-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="2d6d3-104">Применяйте этот шаблон при реализации пользовательских элементов управления, которые используются с механизм привязки данных Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2d6d3-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d6d3-105">Пример</span><span class="sxs-lookup"><span data-stu-id="2d6d3-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2d6d3-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2d6d3-106">Compiling the Code</span></span>  
 <span data-ttu-id="2d6d3-107">Для компиляции в предыдущем примере кода:</span><span class="sxs-lookup"><span data-stu-id="2d6d3-107">To compile the previous code example:</span></span>  
  
-   <span data-ttu-id="2d6d3-108">Вставьте код в пустой файл кода.</span><span class="sxs-lookup"><span data-stu-id="2d6d3-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="2d6d3-109">Необходимо использовать пользовательский элемент управления в форме Windows Forms, который содержит `Main` метод.</span><span class="sxs-lookup"><span data-stu-id="2d6d3-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d6d3-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2d6d3-110">See Also</span></span>  
 [<span data-ttu-id="2d6d3-111">Практическое руководство. Реализация интерфейса INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="2d6d3-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 [<span data-ttu-id="2d6d3-112">Уведомления об изменениях в привязке данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2d6d3-112">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="2d6d3-113">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2d6d3-113">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
