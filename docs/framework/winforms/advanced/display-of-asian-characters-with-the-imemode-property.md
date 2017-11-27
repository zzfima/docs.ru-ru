---
title: "Отображение азиатских символов с помощью свойства ImeMode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Asian languages [Windows Forms], displaying with ImeMode
- Chinese characters [Windows Forms], displaying with ImeMode
- IME mode
- Japanese characters [Windows Forms], displaying with ImeMode
- international applications [Windows Forms], character display
- international characters
- Korean characters
- Asian languages
- Input Method Editor (IME), mode
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4ba86b0c1343d84e65f0e3f9ff48a09b3a80a27a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a><span data-ttu-id="73ccc-102">Отображение азиатских символов с помощью свойства ImeMode</span><span class="sxs-lookup"><span data-stu-id="73ccc-102">Display of Asian Characters with the ImeMode Property</span></span>
<span data-ttu-id="73ccc-103"><xref:System.Windows.Forms.Control.ImeMode%2A> Свойство используется форм и элементов управления для принудительного определенный режим редактора метода ввода (IME).</span><span class="sxs-lookup"><span data-stu-id="73ccc-103">The <xref:System.Windows.Forms.Control.ImeMode%2A> property is used by forms and controls to force a specific mode for an input method editor (IME).</span></span> <span data-ttu-id="73ccc-104">Редактор метода ввода — это необходимый компонент для написания сценариев на китайском, японском и корейском языках, так как количество символов в этих системах письменности превышает возможности кодирования обычной клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="73ccc-104">The IME is an essential component for writing Chinese, Japanese, and Korean scripts, since these writing systems have more characters than can be encoded for a regular keyboard.</span></span> <span data-ttu-id="73ccc-105">Например, в определенном текстовом поле можно разрешить только символы ASCII.</span><span class="sxs-lookup"><span data-stu-id="73ccc-105">For example, you may want to allow only ASCII characters in a particular text box.</span></span> <span data-ttu-id="73ccc-106">В этом случае можно задать <xref:System.Windows.Forms.Control.ImeMode%2A> свойства <xref:System.Windows.Forms.ImeMode> и пользователи только смогут ввести знаки ASCII данное текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="73ccc-106">In such a case you can set the <xref:System.Windows.Forms.Control.ImeMode%2A> property to <xref:System.Windows.Forms.ImeMode> and users will only be able to enter ASCII characters for that particular text box.</span></span> <span data-ttu-id="73ccc-107">Значение по умолчанию <xref:System.Windows.Forms.Control.ImeMode%2A> свойство <xref:System.Windows.Forms.ImeMode>, поэтому если задать свойство для формы, все элементы управления в форме будут наследовать эту настройку.</span><span class="sxs-lookup"><span data-stu-id="73ccc-107">The default value of the <xref:System.Windows.Forms.Control.ImeMode%2A> property is <xref:System.Windows.Forms.ImeMode>, so if you set the property for a form, all controls on the form will inherit that setting.</span></span> <span data-ttu-id="73ccc-108">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.Control.ImeMode%2A> ) и <xref:System.Windows.Forms.ImeMode>.</span><span class="sxs-lookup"><span data-stu-id="73ccc-108">For more information, see <xref:System.Windows.Forms.Control.ImeMode%2A> ) and <xref:System.Windows.Forms.ImeMode>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73ccc-109">См. также</span><span class="sxs-lookup"><span data-stu-id="73ccc-109">See Also</span></span>  
 [<span data-ttu-id="73ccc-110">Глобализация Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73ccc-110">Globalizing Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)
