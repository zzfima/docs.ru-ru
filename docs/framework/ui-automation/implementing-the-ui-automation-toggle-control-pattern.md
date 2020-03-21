---
title: Реализация шаблона элементов управления модели автоматизации пользовательского интерфейса Toggle
ms.date: 03/30/2017
helpviewer_keywords:
- Toggle control pattern
- control patterns, Toggle
- UI Automation, Toggle control pattern
ms.assetid: 3cfe875f-b0c0-413d-9703-5f14e6a1a30e
ms.openlocfilehash: 5f64842d31d46af3d648b9b570d1cfb210e2910a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180067"
---
# <a name="implementing-the-ui-automation-toggle-control-pattern"></a><span data-ttu-id="382fb-102">Реализация шаблона элементов управления модели автоматизации пользовательского интерфейса Toggle</span><span class="sxs-lookup"><span data-stu-id="382fb-102">Implementing the UI Automation Toggle Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="382fb-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="382fb-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="382fb-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="382fb-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="382fb-105">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IToggleProvider>, включая сведения о методах и свойствах.</span><span class="sxs-lookup"><span data-stu-id="382fb-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>, including information about methods and properties.</span></span> <span data-ttu-id="382fb-106">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="382fb-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="382fb-107"><xref:System.Windows.Automation.TogglePattern> Шаблон элемента управления используется для поддержки элементов управления, которые можно переключать между разными состояниями и поддерживать состояние после установки.</span><span class="sxs-lookup"><span data-stu-id="382fb-107">The <xref:System.Windows.Automation.TogglePattern> control pattern is used to support controls that can cycle through a set of states and maintain a state once set.</span></span> <span data-ttu-id="382fb-108">Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="382fb-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="382fb-109">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="382fb-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="382fb-110">При реализации шаблона элемента управления Toggle обратите внимание на следующие правила и соглашения.</span><span class="sxs-lookup"><span data-stu-id="382fb-110">When implementing the Toggle control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="382fb-111">Элементы управления, которые не поддерживают состояние при активации, такие как кнопки, кнопки панели инструментов и гиперссылки, вместо этого шаблона должны реализовывать <xref:System.Windows.Automation.Provider.IInvokeProvider> .</span><span class="sxs-lookup"><span data-stu-id="382fb-111">Controls that do not maintain state when activated, such as buttons, toolbar buttons, and hyperlinks, must implement <xref:System.Windows.Automation.Provider.IInvokeProvider> instead.</span></span>  
  
- <span data-ttu-id="382fb-112">Элемент управления должен проходить по его <xref:System.Windows.Automation.ToggleState> в следующем порядке: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> и если поддерживается — <xref:System.Windows.Automation.ToggleState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="382fb-112">A control must cycle through its <xref:System.Windows.Automation.ToggleState> in the following order: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> and, if supported, <xref:System.Windows.Automation.ToggleState.Indeterminate>.</span></span>  
  
- <span data-ttu-id="382fb-113"><xref:System.Windows.Automation.TogglePattern> не предоставляет метод SetState(newState) из-за проблем, окружающих прямую установку флажка с тремя состояниями без прохода по его соответствующей последовательности <xref:System.Windows.Automation.ToggleState> .</span><span class="sxs-lookup"><span data-stu-id="382fb-113"><xref:System.Windows.Automation.TogglePattern> does not provide a SetState(newState) method due to issues surrounding the direct setting of a tri-state CheckBox without cycling through its appropriate <xref:System.Windows.Automation.ToggleState> sequence.</span></span>  
  
- <span data-ttu-id="382fb-114">Элемент управления RadioButton не реализует <xref:System.Windows.Automation.Provider.IToggleProvider>, так как он не способен пройти по его допустимым состояниям.</span><span class="sxs-lookup"><span data-stu-id="382fb-114">The RadioButton control does not implement <xref:System.Windows.Automation.Provider.IToggleProvider>, as it is not capable of cycling through its valid states.</span></span>  
  
<a name="Required_Members_for_IToggleProvider"></a>
## <a name="required-members-for-itoggleprovider"></a><span data-ttu-id="382fb-115">Обязательные члены для IToggleProvider</span><span class="sxs-lookup"><span data-stu-id="382fb-115">Required Members for IToggleProvider</span></span>  
 <span data-ttu-id="382fb-116">Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IToggleProvider>.</span><span class="sxs-lookup"><span data-stu-id="382fb-116">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>.</span></span>  
  
|<span data-ttu-id="382fb-117">Обязательный член</span><span class="sxs-lookup"><span data-stu-id="382fb-117">Required member</span></span>|<span data-ttu-id="382fb-118">Тип члена</span><span class="sxs-lookup"><span data-stu-id="382fb-118">Member type</span></span>|<span data-ttu-id="382fb-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="382fb-119">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.TogglePattern.Toggle%2A>|<span data-ttu-id="382fb-120">Метод</span><span class="sxs-lookup"><span data-stu-id="382fb-120">Method</span></span>|<span data-ttu-id="382fb-121">None</span><span class="sxs-lookup"><span data-stu-id="382fb-121">None</span></span>|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|<span data-ttu-id="382fb-122">Свойство</span><span class="sxs-lookup"><span data-stu-id="382fb-122">Property</span></span>|<span data-ttu-id="382fb-123">None</span><span class="sxs-lookup"><span data-stu-id="382fb-123">None</span></span>|  
  
 <span data-ttu-id="382fb-124">Этот шаблон элемента управления не имеет связанных событий.</span><span class="sxs-lookup"><span data-stu-id="382fb-124">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="382fb-125">Исключения</span><span class="sxs-lookup"><span data-stu-id="382fb-125">Exceptions</span></span>  
 <span data-ttu-id="382fb-126">Этот шаблон элемента управления не имеет связанных исключений.</span><span class="sxs-lookup"><span data-stu-id="382fb-126">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="382fb-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="382fb-127">See also</span></span>

- [<span data-ttu-id="382fb-128">UI Automation Control Patterns Overview</span><span class="sxs-lookup"><span data-stu-id="382fb-128">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="382fb-129">Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="382fb-129">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="382fb-130">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="382fb-130">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="382fb-131">Получение состояния флажка с использованием автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="382fb-131">Get the Toggle State of a Check Box Using UI Automation</span></span>](get-the-toggle-state-of-a-check-box-using-ui-automation.md)
- [<span data-ttu-id="382fb-132">UI Automation Tree Overview</span><span class="sxs-lookup"><span data-stu-id="382fb-132">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="382fb-133">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="382fb-133">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
