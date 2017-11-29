---
title: "Обеспечение безопасности данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bd41f5174f426e723ea7e069eaee8f2d367625a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="securing-state-data"></a><span data-ttu-id="a71f5-102">Обеспечение безопасности данных</span><span class="sxs-lookup"><span data-stu-id="a71f5-102">Securing State Data</span></span>
<span data-ttu-id="a71f5-103">Приложения, работающие с конфиденциальными данными или принимающие любые решения по организации безопасности, должны сохранять эти данные под своим непосредственным управлением и не должны позволять потенциально вредоносному коду напрямую получать доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="a71f5-103">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="a71f5-104">Лучшим способом защиты данных в памяти является объявление этих данных как закрытых или внутренних переменных (с областью, ограниченной той же сборкой).</span><span class="sxs-lookup"><span data-stu-id="a71f5-104">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="a71f5-105">Однако не следует забывать, что даже к этим данным применяются права доступа.</span><span class="sxs-lookup"><span data-stu-id="a71f5-105">However, even this data is subject to access you should be aware of:</span></span>  
  
-   <span data-ttu-id="a71f5-106">С помощью механизмов отражения код с высоким доверием, способный ссылаться на ваш объект, может получать и устанавливать закрытые члены.</span><span class="sxs-lookup"><span data-stu-id="a71f5-106">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
-   <span data-ttu-id="a71f5-107">С помощью сериализации код с высоким доверием может эффективно получать и устанавливать закрытые члены, если он имеет доступ к соответствующим данным в сериализованной форме объекта.</span><span class="sxs-lookup"><span data-stu-id="a71f5-107">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
-   <span data-ttu-id="a71f5-108">Эти данные могут считываться в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="a71f5-108">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="a71f5-109">Убедитесь, что ни один из ваших собственных методов или свойств не предоставляет непреднамеренно эти значения.</span><span class="sxs-lookup"><span data-stu-id="a71f5-109">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a71f5-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a71f5-110">See Also</span></span>  
 [<span data-ttu-id="a71f5-111">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="a71f5-111">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
