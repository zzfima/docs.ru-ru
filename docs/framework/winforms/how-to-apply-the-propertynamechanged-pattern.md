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
ms.openlocfilehash: 01afa713e97206ea192ba55dc2affad20163f872
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665266"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="e2545-102">Практическое руководство. Применение шаблона PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="e2545-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="e2545-103">В следующем примере кода демонстрируется применение *PropertyName*Changed шаблон для пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e2545-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="e2545-104">Применяйте этот шаблон при реализации пользовательских элементов управления, используемых с ними механизм привязки данных Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e2545-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2545-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e2545-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e2545-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e2545-106">Compiling the Code</span></span>  
 <span data-ttu-id="e2545-107">Для компиляции в предыдущем примере кода:</span><span class="sxs-lookup"><span data-stu-id="e2545-107">To compile the previous code example:</span></span>  
  
- <span data-ttu-id="e2545-108">Вставьте код в пустой файл кода.</span><span class="sxs-lookup"><span data-stu-id="e2545-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="e2545-109">Необходимо использовать пользовательский элемент управления на форму Windows, которая содержит `Main` метод.</span><span class="sxs-lookup"><span data-stu-id="e2545-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2545-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e2545-110">See also</span></span>

- [<span data-ttu-id="e2545-111">Практическое руководство. Реализация интерфейса INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="e2545-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)
- [<span data-ttu-id="e2545-112">Уведомления об изменениях в привязке данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e2545-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="e2545-113">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e2545-113">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
