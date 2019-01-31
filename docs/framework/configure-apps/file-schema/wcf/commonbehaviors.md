---
title: <commonBehaviors>
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 73bf759fd3dfa87398aa74de93160a4ffce08eba
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268765"
---
# <a name="commonbehaviors"></a><span data-ttu-id="e1d60-101">\<commonBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e1d60-101">\<commonBehaviors></span></span>
<span data-ttu-id="e1d60-102">Раздел `commonBehaviors` может определяться только в файле machine.config.</span><span class="sxs-lookup"><span data-stu-id="e1d60-102">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="e1d60-103">В нем определяются две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="e1d60-103">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="e1d60-104">Каждая коллекция определяет элементы поведения, используемые соответственно всеми конечными точками WCF и службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e1d60-104">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="e1d60-105">Поведения, определенные в `endpointBehaviors`, применяются только к клиентам, а поведения, определенные в `serviceBehaviors`, применяются только к службам.</span><span class="sxs-lookup"><span data-stu-id="e1d60-105">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="e1d60-106">Если поведение определяется как в разделе `commonBehaviors`, так и в разделе `behaviors`, преимущество имеет поведение в разделе `behaviors`.</span><span class="sxs-lookup"><span data-stu-id="e1d60-106">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
