---
title: Обеспечение безопасности данных
description: Объявить данные состояния как частные или внутренние переменные, чтобы ограничить доступ к ним. К таким данным по-прежнему можно получить доступ через отражение, сериализацию и отладку.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
ms.openlocfilehash: f95bf409f7eef8c2636d3c180d2bbd95fbc689c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186822"
---
# <a name="securing-state-data"></a><span data-ttu-id="971f0-104">Обеспечение безопасности данных</span><span class="sxs-lookup"><span data-stu-id="971f0-104">Securing State Data</span></span>
<span data-ttu-id="971f0-105">Приложения, работающие с конфиденциальными данными или принимающие любые решения по организации безопасности, должны сохранять эти данные под своим непосредственным управлением и не должны позволять потенциально вредоносному коду напрямую получать доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="971f0-105">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="971f0-106">Лучшим способом защиты данных в памяти является объявление этих данных как закрытых или внутренних переменных (с областью, ограниченной той же сборкой).</span><span class="sxs-lookup"><span data-stu-id="971f0-106">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="971f0-107">Однако не следует забывать, что даже к этим данным применяются права доступа.</span><span class="sxs-lookup"><span data-stu-id="971f0-107">However, even this data is subject to access you should be aware of:</span></span>  
  
- <span data-ttu-id="971f0-108">С помощью механизмов отражения код с высоким доверием, способный ссылаться на ваш объект, может получать и устанавливать закрытые члены.</span><span class="sxs-lookup"><span data-stu-id="971f0-108">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
- <span data-ttu-id="971f0-109">С помощью сериализации код с высоким доверием может эффективно получать и устанавливать закрытые члены, если он имеет доступ к соответствующим данным в сериализованной форме объекта.</span><span class="sxs-lookup"><span data-stu-id="971f0-109">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
- <span data-ttu-id="971f0-110">Эти данные могут считываться в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="971f0-110">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="971f0-111">Убедитесь, что ни один из ваших собственных методов или свойств не предоставляет непреднамеренно эти значения.</span><span class="sxs-lookup"><span data-stu-id="971f0-111">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="971f0-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="971f0-112">See also</span></span>

- [<span data-ttu-id="971f0-113">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="971f0-113">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
