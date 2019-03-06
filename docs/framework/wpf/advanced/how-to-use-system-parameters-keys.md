---
title: Практическое руководство. Использование разделов системных параметров
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: a71551c5d539d7009fb9a052c81928a009fc4c35
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357200"
---
# <a name="how-to-use-system-parameters-keys"></a><span data-ttu-id="bae07-102">Практическое руководство. Использование разделов системных параметров</span><span class="sxs-lookup"><span data-stu-id="bae07-102">How to: Use System Parameters Keys</span></span>
<span data-ttu-id="bae07-103">Системные ресурсы предоставляют ряд метрик системы в качестве ресурсов, что помогает разработчикам создавать визуальные элементы, совместимые с параметрами системы.</span><span class="sxs-lookup"><span data-stu-id="bae07-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="bae07-104"><xref:System.Windows.SystemParameters> — Это класс, который содержит значения системных параметров и ключи ресурсов, которые привязаны к значениям — например, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> и <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="bae07-104"><xref:System.Windows.SystemParameters> is a class that contains both system parameter values and resource keys that bind to the values—for example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span></span> <span data-ttu-id="bae07-105">Метрики параметров системы могут использоваться в качестве статических или динамических ресурсов.</span><span class="sxs-lookup"><span data-stu-id="bae07-105">System parameter metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="bae07-106">Используйте динамический ресурс, если требуется метрика параметра для автоматического обновления во время выполнения приложения; в других случаях используйте статический ресурс.</span><span class="sxs-lookup"><span data-stu-id="bae07-106">Use a dynamic resource if you want the parameter metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bae07-107">Динамические ресурсы имеют ключевое слово *ключ* добавляется к имени свойства.</span><span class="sxs-lookup"><span data-stu-id="bae07-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="bae07-108">В приведенном ниже примере показано, как получить доступ к ресурсам динамических параметров системы и использовать их для создания стиля или настройки кнопки.</span><span class="sxs-lookup"><span data-stu-id="bae07-108">The following example shows how to access and use system parameter dynamic resources to style or customize a button.</span></span> <span data-ttu-id="bae07-109">Это [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] примере размеры кнопки путем назначения <xref:System.Windows.SystemParameters> значения ширины и высоты кнопки.</span><span class="sxs-lookup"><span data-stu-id="bae07-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example sizes a button by assigning <xref:System.Windows.SystemParameters> values to the button's width and height.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bae07-110">Пример</span><span class="sxs-lookup"><span data-stu-id="bae07-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="bae07-111">См. также</span><span class="sxs-lookup"><span data-stu-id="bae07-111">See also</span></span>
- [<span data-ttu-id="bae07-112">Заливка области с помощью системной кисти</span><span class="sxs-lookup"><span data-stu-id="bae07-112">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="bae07-113">Использование SystemFonts</span><span class="sxs-lookup"><span data-stu-id="bae07-113">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
- [<span data-ttu-id="bae07-114">Использование SystemParameters</span><span class="sxs-lookup"><span data-stu-id="bae07-114">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
