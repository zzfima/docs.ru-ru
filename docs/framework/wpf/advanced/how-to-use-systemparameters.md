---
title: "Как использовать SystemParameters"
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
helpviewer_keywords: classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec333fbc30374ff6f8e2e7674ab332644ff7aad0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-systemparameters"></a><span data-ttu-id="5440a-102">Как использовать SystemParameters</span><span class="sxs-lookup"><span data-stu-id="5440a-102">How to: Use SystemParameters</span></span>
<span data-ttu-id="5440a-103">В этом примере показано, как получить доступ и использование свойств объекта <xref:System.Windows.SystemParameters> для изменения стиля или настроек кнопки.</span><span class="sxs-lookup"><span data-stu-id="5440a-103">This example shows how to access and use the properties of <xref:System.Windows.SystemParameters> in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5440a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="5440a-104">Example</span></span>  
 <span data-ttu-id="5440a-105">Системные ресурсы предоставляют несколько параметров системы в виде ресурсов, помогающих создавать визуальные элементы с учетом параметров системы.</span><span class="sxs-lookup"><span data-stu-id="5440a-105">System resources expose several system based settings as resources in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="5440a-106"><xref:System.Windows.SystemParameters>— Это класс, содержащий свойства значений параметров системы и ключи ресурсов, которые привязаны к значениям.</span><span class="sxs-lookup"><span data-stu-id="5440a-106"><xref:System.Windows.SystemParameters> is a class that contains both system parameter value properties, and resource keys that bind to the values.</span></span> <span data-ttu-id="5440a-107">Например <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> — <xref:System.Windows.SystemParameters> значение свойства и <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> является соответствующим ключом ресурса.</span><span class="sxs-lookup"><span data-stu-id="5440a-107">For example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> is a <xref:System.Windows.SystemParameters> property value and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> is the corresponding resource key.</span></span>  
  
 <span data-ttu-id="5440a-108">В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], можно использовать члены <xref:System.Windows.SystemParameters> как статическое свойство или динамические ссылки на ресурс (со статическим значением свойства в качестве ключа).</span><span class="sxs-lookup"><span data-stu-id="5440a-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemParameters> as either a static property usage, or a dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="5440a-109">Используйте ссылку на динамический ресурс, если требуется системное значение для автоматического обновления во время выполнения приложения. В противном случае используйте статическую ссылку.</span><span class="sxs-lookup"><span data-stu-id="5440a-109">Use a dynamic resource reference if you want the system based value to update automatically while the application runs; otherwise, use a static reference.</span></span> <span data-ttu-id="5440a-110">Ключи ресурсов имеют суффикс `Key` добавляется к имени свойства.</span><span class="sxs-lookup"><span data-stu-id="5440a-110">Resource keys have the suffix `Key` appended to the property name.</span></span>  
  
 <span data-ttu-id="5440a-111">Приведенный ниже показано, как получить доступ и использовать статические значения <xref:System.Windows.SystemParameters> для стиля или настройки кнопки.</span><span class="sxs-lookup"><span data-stu-id="5440a-111">The following example shows how to access and use the static values of <xref:System.Windows.SystemParameters> to style or customize a button.</span></span> <span data-ttu-id="5440a-112">Этот пример разметки изменяет размер кнопки, применяя <xref:System.Windows.SystemParameters> кнопке значения.</span><span class="sxs-lookup"><span data-stu-id="5440a-112">This markup example sizes a button by applying <xref:System.Windows.SystemParameters> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 <span data-ttu-id="5440a-113">Чтобы использовать значения из <xref:System.Windows.SystemParameters> в коде, не нужно использовать статические или динамические ссылки на ресурс.</span><span class="sxs-lookup"><span data-stu-id="5440a-113">To use the values of <xref:System.Windows.SystemParameters> in code, you do not have to use either static references or dynamic resource references.</span></span> <span data-ttu-id="5440a-114">Вместо этого используйте значения <xref:System.Windows.SystemParameters> класса.</span><span class="sxs-lookup"><span data-stu-id="5440a-114">Instead, use the values of the <xref:System.Windows.SystemParameters> class.</span></span> <span data-ttu-id="5440a-115">Хотя неключевые свойства очевидно определены как статические, поведение среды выполнения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , размещенного в системе будет пересчитывать свойства в режиме реального времени и правильно учитывать управляемые пользователем изменения значений системы.</span><span class="sxs-lookup"><span data-stu-id="5440a-115">Although the non-key properties are apparently defined as static properties, the runtime behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in realtime, and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="5440a-116">В следующем примере показано, как задать ширину и высоту кнопки с помощью <xref:System.Windows.SystemParameters> значения.</span><span class="sxs-lookup"><span data-stu-id="5440a-116">The following example shows how to set the width and height of a button by using <xref:System.Windows.SystemParameters> values.</span></span>  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="5440a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5440a-117">See Also</span></span>  
 <xref:System.Windows.SystemParameters>  
 [<span data-ttu-id="5440a-118">Заливка области с помощью системной кисти</span><span class="sxs-lookup"><span data-stu-id="5440a-118">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="5440a-119">Использование SystemFonts</span><span class="sxs-lookup"><span data-stu-id="5440a-119">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [<span data-ttu-id="5440a-120">Использование разделов системных параметров</span><span class="sxs-lookup"><span data-stu-id="5440a-120">Use System Parameters Keys</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)  
 [<span data-ttu-id="5440a-121">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="5440a-121">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
