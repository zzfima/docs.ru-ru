---
title: Практическое руководство. Применение шаблона PropertyNameChanged
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 775a27b1b4ba8143e297a3c4d323356a304073a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="0ee2c-102">Практическое руководство. Применение шаблона PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="0ee2c-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="0ee2c-103">В следующем примере кода демонстрируется применение *PropertyName*шаблон Changed к пользовательскому элементу управления.</span><span class="sxs-lookup"><span data-stu-id="0ee2c-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="0ee2c-104">Применяйте этот шаблон при реализации пользовательских элементов управления, которые используются с механизм привязки данных Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0ee2c-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ee2c-105">Пример</span><span class="sxs-lookup"><span data-stu-id="0ee2c-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0ee2c-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0ee2c-106">Compiling the Code</span></span>  
 <span data-ttu-id="0ee2c-107">Для компиляции в предыдущем примере кода:</span><span class="sxs-lookup"><span data-stu-id="0ee2c-107">To compile the previous code example:</span></span>  
  
-   <span data-ttu-id="0ee2c-108">Вставьте код в пустой файл кода.</span><span class="sxs-lookup"><span data-stu-id="0ee2c-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="0ee2c-109">Необходимо использовать пользовательский элемент управления в форме Windows Forms, который содержит `Main` метод.</span><span class="sxs-lookup"><span data-stu-id="0ee2c-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee2c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0ee2c-110">See Also</span></span>  
 [<span data-ttu-id="0ee2c-111">Практическое руководство. Реализация интерфейса INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="0ee2c-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 [<span data-ttu-id="0ee2c-112">Уведомления об изменениях в привязке данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ee2c-112">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="0ee2c-113">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ee2c-113">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
