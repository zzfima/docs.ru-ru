---
title: Обеспечение безопасности данных
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c821177ca897e617885425217ac0b6659b5ea6e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44212234"
---
# <a name="securing-state-data"></a><span data-ttu-id="15537-102">Обеспечение безопасности данных</span><span class="sxs-lookup"><span data-stu-id="15537-102">Securing State Data</span></span>
<span data-ttu-id="15537-103">Приложения, работающие с конфиденциальными данными или принимающие любые решения по организации безопасности, должны сохранять эти данные под своим непосредственным управлением и не должны позволять потенциально вредоносному коду напрямую получать доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="15537-103">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="15537-104">Лучшим способом защиты данных в памяти является объявление этих данных как закрытых или внутренних переменных (с областью, ограниченной той же сборкой).</span><span class="sxs-lookup"><span data-stu-id="15537-104">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="15537-105">Однако не следует забывать, что даже к этим данным применяются права доступа.</span><span class="sxs-lookup"><span data-stu-id="15537-105">However, even this data is subject to access you should be aware of:</span></span>  
  
-   <span data-ttu-id="15537-106">С помощью механизмов отражения код с высоким доверием, способный ссылаться на ваш объект, может получать и устанавливать закрытые члены.</span><span class="sxs-lookup"><span data-stu-id="15537-106">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
-   <span data-ttu-id="15537-107">С помощью сериализации код с высоким доверием может эффективно получать и устанавливать закрытые члены, если он имеет доступ к соответствующим данным в сериализованной форме объекта.</span><span class="sxs-lookup"><span data-stu-id="15537-107">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
-   <span data-ttu-id="15537-108">Эти данные могут считываться в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="15537-108">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="15537-109">Убедитесь, что ни один из ваших собственных методов или свойств не предоставляет непреднамеренно эти значения.</span><span class="sxs-lookup"><span data-stu-id="15537-109">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15537-110">См. также</span><span class="sxs-lookup"><span data-stu-id="15537-110">See also</span></span>

- [<span data-ttu-id="15537-111">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="15537-111">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
