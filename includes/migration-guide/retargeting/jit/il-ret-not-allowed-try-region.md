---
ms.openlocfilehash: 060da3ebc60057554fd572bd2569652afee6bd0f
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761145"
---
### <a name="il-ret-not-allowed-in-a-try-region"></a><span data-ttu-id="521f6-101">Инструкция IL ret недопустима в области try</span><span class="sxs-lookup"><span data-stu-id="521f6-101">IL ret not allowed in a try region</span></span>

|   |   |
|---|---|
|<span data-ttu-id="521f6-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="521f6-102">Details</span></span>|<span data-ttu-id="521f6-103">В отличие от JIT-компилятора JIT64, компилятор RyuJIT (в .NET Framework 4.6) не разрешает инструкцию IL ret в области try.</span><span class="sxs-lookup"><span data-stu-id="521f6-103">Unlike the JIT64 just-in-time compiler, RyuJIT (used in .NET Framework 4.6) does not allow an IL ret instruction in a try region.</span></span> <span data-ttu-id="521f6-104">Возврат из области try запрещен в спецификации ECMA-335, и ни один известный управляемый компилятор не создает такие IL.</span><span class="sxs-lookup"><span data-stu-id="521f6-104">Returning from a try region is disallowed by the ECMA-335 specification, and no known managed compiler generates such IL.</span></span> <span data-ttu-id="521f6-105">Однако компилятор JIT64 выполнит такие IL, если они созданы с помощью порождения отражения.</span><span class="sxs-lookup"><span data-stu-id="521f6-105">However, the JIT64 compiler will execute such IL if it is generated using reflection emit.</span></span>|
|<span data-ttu-id="521f6-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="521f6-106">Suggestion</span></span>|<span data-ttu-id="521f6-107">Если приложение создает IL, который включает в себя код операции ret в области try, это приложение можно нацелить на платформу .NET Framework 4.5, чтобы использовать старый JIT-компилятор и избежать этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="521f6-107">If an app is generating IL that includes a ret opcode in a try region, the app may target .NET Framework 4.5 to use the old JIT and avoid this break.</span></span> <span data-ttu-id="521f6-108">Кроме того, создаваемый IL-код можно обновить, чтобы он возвращался после области try.</span><span class="sxs-lookup"><span data-stu-id="521f6-108">Alternatively, the generated IL may be updated to return after the try region.</span></span>|
|<span data-ttu-id="521f6-109">Область</span><span class="sxs-lookup"><span data-stu-id="521f6-109">Scope</span></span>|<span data-ttu-id="521f6-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="521f6-110">Edge</span></span>|
|<span data-ttu-id="521f6-111">Версия</span><span class="sxs-lookup"><span data-stu-id="521f6-111">Version</span></span>|<span data-ttu-id="521f6-112">4.6</span><span class="sxs-lookup"><span data-stu-id="521f6-112">4.6</span></span>|
|<span data-ttu-id="521f6-113">Тип</span><span class="sxs-lookup"><span data-stu-id="521f6-113">Type</span></span>|<span data-ttu-id="521f6-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="521f6-114">Retargeting</span></span>|

