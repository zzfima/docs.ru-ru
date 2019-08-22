---
title: Использование элементов управления WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5ea92b24a2ca30c0ad137d83c8f521a952ad0c6b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658490"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a><span data-ttu-id="f942e-102">Использование элементов управления WPF в Windows Forms приложениях</span><span class="sxs-lookup"><span data-stu-id="f942e-102">Use WPF controls in Windows Forms apps</span></span>

<span data-ttu-id="f942e-103">Элементы управления Windows Presentation Foundation (WPF) можно использовать в приложениях на основе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f942e-103">You can use Windows Presentation Foundation (WPF) controls in Windows Forms-based applications.</span></span> <span data-ttu-id="f942e-104">Хотя это две различные технологии представления, они беспрепятственно взаимодействуют.</span><span class="sxs-lookup"><span data-stu-id="f942e-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="f942e-105">Конструктор Windows Forms в Visual Studio предоставляет среду визуального проектирования для размещения элементов управления Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="f942e-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="f942e-106">Элемент управления WPF размещается на специальном элементе управления Windows Forms с <xref:System.Windows.Forms.Integration.ElementHost>именем.</span><span class="sxs-lookup"><span data-stu-id="f942e-106">A WPF control is hosted by a special Windows Forms control that's named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="f942e-107">Этот элемент управления позволяет элементу управления WPF участвовать в макете формы и принимать сообщения клавиатуры и мыши.</span><span class="sxs-lookup"><span data-stu-id="f942e-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="f942e-108">Во время разработки можно разместить <xref:System.Windows.Forms.Integration.ElementHost> элемент управления так же, как любой Windows Forms управления.</span><span class="sxs-lookup"><span data-stu-id="f942e-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="f942e-109">Можно также использовать элементы управления Windows Forms в приложениях на основе WPF.</span><span class="sxs-lookup"><span data-stu-id="f942e-109">You can also use Windows Forms controls in WPF-based applications.</span></span> <span data-ttu-id="f942e-110">Дополнительные сведения см. [в разделе Разработка XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="f942e-110">For more information, see [Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span></span>

## <a name="see-also"></a><span data-ttu-id="f942e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f942e-111">See also</span></span>

- [<span data-ttu-id="f942e-112">Взаимодействие WPF и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f942e-112">WPF and Windows Forms interoperation</span></span>](/dotnet/framework/wpf/advanced/wpf-and-windows-forms-interoperation)
