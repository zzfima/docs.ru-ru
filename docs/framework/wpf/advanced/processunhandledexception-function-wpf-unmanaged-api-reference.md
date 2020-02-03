---
title: Функция Процессунхандледексцептион — Справочник по неуправляемым API в WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 757e5ac3aa2dc4c87b210b026998523bd82045c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743923"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="e4ce7-102">Функция Процессунхандледексцептион (Справочник по неуправляемым интерфейсам API WPF)</span><span class="sxs-lookup"><span data-stu-id="e4ce7-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="e4ce7-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для непосредственного использования из кода.</span><span class="sxs-lookup"><span data-stu-id="e4ce7-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="e4ce7-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="e4ce7-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4ce7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4ce7-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4ce7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e4ce7-106">Parameters</span></span>  
 <span data-ttu-id="e4ce7-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="e4ce7-107">errorMsg</span></span>  
 <span data-ttu-id="e4ce7-108">Сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e4ce7-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4ce7-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e4ce7-109">Requirements</span></span>  
 <span data-ttu-id="e4ce7-110">**Платформы:** См. [.NET Framework требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4ce7-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4ce7-111">**КОМПОНОВКИ**</span><span class="sxs-lookup"><span data-stu-id="e4ce7-111">**DLL:**</span></span>  
  
 <span data-ttu-id="e4ce7-112">В .NET Framework 3,0 и 3,5: Пресентатионхостдлл. dll</span><span class="sxs-lookup"><span data-stu-id="e4ce7-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="e4ce7-113">В .NET Framework 4 и более поздних версиях: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="e4ce7-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="e4ce7-114">**Версия .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4ce7-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4ce7-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e4ce7-115">See also</span></span>

- [<span data-ttu-id="e4ce7-116">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="e4ce7-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
