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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62030359"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="eb570-102">Функция ProcessUnhandledException (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="eb570-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="eb570-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="eb570-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="eb570-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="eb570-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb570-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb570-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb570-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="eb570-106">Parameters</span></span>  
 <span data-ttu-id="eb570-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="eb570-107">errorMsg</span></span>  
 <span data-ttu-id="eb570-108">Сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="eb570-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb570-109">Требования</span><span class="sxs-lookup"><span data-stu-id="eb570-109">Requirements</span></span>  
 <span data-ttu-id="eb570-110">**Платформы:** См. в разделе [системные требования .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb570-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb570-111">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="eb570-111">**DLL:**</span></span>  
  
 <span data-ttu-id="eb570-112">В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="eb570-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="eb570-113">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="eb570-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="eb570-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb570-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb570-115">См. также</span><span class="sxs-lookup"><span data-stu-id="eb570-115">See also</span></span>

- [<span data-ttu-id="eb570-116">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="eb570-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
