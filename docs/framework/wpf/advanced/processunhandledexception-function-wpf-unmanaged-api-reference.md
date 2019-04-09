---
title: Функция ProcessUnhandledException (WPF Справочник по неуправляемым API)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 0c8751454be6e0eed547c38e9d0bc7931abaec3d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196974"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="be4f6-102">Функция ProcessUnhandledException (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="be4f6-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="be4f6-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="be4f6-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="be4f6-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="be4f6-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be4f6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be4f6-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="be4f6-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="be4f6-106">Parameters</span></span>  
 <span data-ttu-id="be4f6-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="be4f6-107">errorMsg</span></span>  
 <span data-ttu-id="be4f6-108">Сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="be4f6-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be4f6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="be4f6-109">Requirements</span></span>  
 <span data-ttu-id="be4f6-110">**Платформы:** См. в разделе [системные требования .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be4f6-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 **<span data-ttu-id="be4f6-111">БИБЛИОТЕКА DLL:</span><span class="sxs-lookup"><span data-stu-id="be4f6-111">DLL:</span></span>**  
  
 <span data-ttu-id="be4f6-112">В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="be4f6-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="be4f6-113">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="be4f6-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 **<span data-ttu-id="be4f6-114">Версии платформы .NET framework:</span><span class="sxs-lookup"><span data-stu-id="be4f6-114">.NET Framework Version:</span></span>** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="be4f6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="be4f6-115">See also</span></span>

- [<span data-ttu-id="be4f6-116">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="be4f6-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
