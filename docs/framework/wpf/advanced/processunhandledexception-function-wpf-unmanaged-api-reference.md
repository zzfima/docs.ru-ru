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
ms.openlocfilehash: 73480f7cd8be7bcb5296782a8503eb689442a14c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578644"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="97d6b-102">Функция ProcessUnhandledException (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="97d6b-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="97d6b-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="97d6b-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="97d6b-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="97d6b-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97d6b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97d6b-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97d6b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="97d6b-106">Parameters</span></span>  
 <span data-ttu-id="97d6b-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="97d6b-107">errorMsg</span></span>  
 <span data-ttu-id="97d6b-108">Сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="97d6b-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97d6b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="97d6b-109">Requirements</span></span>  
 <span data-ttu-id="97d6b-110">**Платформы:** См. в разделе [системные требования .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97d6b-110">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97d6b-111">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="97d6b-111">**DLL:**</span></span>  
  
 <span data-ttu-id="97d6b-112">В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="97d6b-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="97d6b-113">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="97d6b-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="97d6b-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97d6b-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97d6b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="97d6b-115">See also</span></span>
- [<span data-ttu-id="97d6b-116">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="97d6b-116">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
