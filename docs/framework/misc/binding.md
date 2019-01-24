---
title: '&lt;Привязки&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 666183d6-4d1f-45c7-ac64-bdf93ee8f36f
ms.openlocfilehash: fb4fafda31205e2ce5efd01ab265fcacfa70bdf6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539198"
---
# <a name="ltbindinggt"></a><span data-ttu-id="b5d71-102">&lt;Привязки&gt;</span><span class="sxs-lookup"><span data-stu-id="b5d71-102">&lt;binding&gt;</span></span>
<span data-ttu-id="b5d71-103">Элемент `binding` используется для настройки различных типов стандартных привязок, которые предоставляются в Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="b5d71-103">You can use the `binding` element to configure different types of predefined bindings provided by Windows Communication Foundation (WCF).</span></span>  
  
## <a name="system-provided-binding"></a><span data-ttu-id="b5d71-104">Привязка, предоставляемая системой</span><span class="sxs-lookup"><span data-stu-id="b5d71-104">System-Provided Binding</span></span>  
 <span data-ttu-id="b5d71-105">Привязки, предоставляемые системой, скрывают сложность стека обмена сообщениями WCF.</span><span class="sxs-lookup"><span data-stu-id="b5d71-105">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="b5d71-106">Приложениям, использующим предоставляемые системой привязки, не требуется полный контроль над стеком.</span><span class="sxs-lookup"><span data-stu-id="b5d71-106">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="b5d71-107">Атрибутами в каждой привязке, предоставляемой системой, являются атрибуты, наиболее подходящие для области применения привязки.</span><span class="sxs-lookup"><span data-stu-id="b5d71-107">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>  
  
 <span data-ttu-id="b5d71-108">В разделе конфигурации для каждой привязки, предоставляемой системой, можно определить несколько конфигураций, используемых для настройки привязки.</span><span class="sxs-lookup"><span data-stu-id="b5d71-108">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="b5d71-109">Каждая конфигурация идентифицируется по уникальному имени.</span><span class="sxs-lookup"><span data-stu-id="b5d71-109">Each configuration is identified by a unique name.</span></span>  
  
 <span data-ttu-id="b5d71-110">К привязке, предоставляемой системой, невозможно добавить элементы или атрибуты.</span><span class="sxs-lookup"><span data-stu-id="b5d71-110">It is not possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="b5d71-111">Чтобы получить такую возможность, необходимо реализовать пользовательскую привязку в соответствии с инструкциями в разделе «Пользовательская привязка».</span><span class="sxs-lookup"><span data-stu-id="b5d71-111">To do so, you should implement a custom binding as described in the "Custom Binding" section of this topic.</span></span> <span data-ttu-id="b5d71-112">Можно определить пользовательскую привязку, которая полностью повторяет предоставляемую системой привязку и добавляет несколько параметров, контроль над которыми нужен пользовательскому приложению.</span><span class="sxs-lookup"><span data-stu-id="b5d71-112">It is possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  
  
## <a name="custom-binding"></a><span data-ttu-id="b5d71-113">Пользовательская привязка</span><span class="sxs-lookup"><span data-stu-id="b5d71-113">Custom Binding</span></span>  
 <span data-ttu-id="b5d71-114">Пользовательские привязки предоставляют полный контроль над стеком обмена сообщениями WCF.</span><span class="sxs-lookup"><span data-stu-id="b5d71-114">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="b5d71-115">Отдельная привязка определяет стек обмена сообщениями, задавая элементы конфигурации для элементов стека в том порядке, в котором они присутствуют в стеке.</span><span class="sxs-lookup"><span data-stu-id="b5d71-115">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="b5d71-116">Каждый элемент определяет и задает параметры одного элемента стека.</span><span class="sxs-lookup"><span data-stu-id="b5d71-116">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="b5d71-117">В каждой пользовательской привязке должен быть один и только один элемент `transport`.</span><span class="sxs-lookup"><span data-stu-id="b5d71-117">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="b5d71-118">Без этого элемента стек обмена сообщениями является неполным.</span><span class="sxs-lookup"><span data-stu-id="b5d71-118">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="b5d71-119">Важен порядок, в котором элементы присутствуют в стеке, поскольку именно в этом порядке к сообщению применяются операции.</span><span class="sxs-lookup"><span data-stu-id="b5d71-119">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="b5d71-120">Рекомендуется следующий порядок элементов стека:</span><span class="sxs-lookup"><span data-stu-id="b5d71-120">The recommended order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="b5d71-121">Транзакции (необязательный)</span><span class="sxs-lookup"><span data-stu-id="b5d71-121">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="b5d71-122">Надежный обмен сообщениями (необязательный)</span><span class="sxs-lookup"><span data-stu-id="b5d71-122">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="b5d71-123">Безопасность (необязательный)</span><span class="sxs-lookup"><span data-stu-id="b5d71-123">Security (optional)</span></span>  
  
4.  <span data-ttu-id="b5d71-124">Кодировщик</span><span class="sxs-lookup"><span data-stu-id="b5d71-124">Encoder</span></span>  
  
5.  <span data-ttu-id="b5d71-125">Transport</span><span class="sxs-lookup"><span data-stu-id="b5d71-125">Transport</span></span>  
  
 <span data-ttu-id="b5d71-126">Пользовательские привязки идентифицируются по атрибуту `name`.</span><span class="sxs-lookup"><span data-stu-id="b5d71-126">Custom bindings are identified by their `name` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5d71-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b5d71-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- [<span data-ttu-id="b5d71-128">Привязки</span><span class="sxs-lookup"><span data-stu-id="b5d71-128">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b5d71-129">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="b5d71-129">Custom Bindings</span></span>](../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b5d71-130">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b5d71-130">\<customBinding></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
