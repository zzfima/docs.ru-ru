---
title: "Функция ForwardTranslateAccelerator (WPF Справочник по неуправляемым API)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ForwardTranslateAccelerator
api_location: PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cca9c78eaf13e04d22fce9f61ce4a7ab9ee09769
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="5d6a6-102">Функция ForwardTranslateAccelerator (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="5d6a6-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="5d6a6-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="5d6a6-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления windows.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d6a6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d6a6-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d6a6-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d6a6-106">Parameters</span></span>  
 <span data-ttu-id="5d6a6-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="5d6a6-107">pMsg</span></span>  
 <span data-ttu-id="5d6a6-108">Указатель на сообщение.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="5d6a6-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="5d6a6-109">appUnhandled</span></span>  
 <span data-ttu-id="5d6a6-110">`true`Если приложение уже был установлен возможность для обработки входящего сообщения, но не предусмотрена. в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d6a6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5d6a6-111">Requirements</span></span>  
 <span data-ttu-id="5d6a6-112">**Платформы:** разделе [требования к системе для .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d6a6-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d6a6-113">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="5d6a6-113">**DLL:**</span></span>  
  
 <span data-ttu-id="5d6a6-114">В платформе .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="5d6a6-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="5d6a6-115">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="5d6a6-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="5d6a6-116">**Версия платформы .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d6a6-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d6a6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5d6a6-117">See Also</span></span>  
 [<span data-ttu-id="5d6a6-118">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="5d6a6-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
