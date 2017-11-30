---
title: "Функция SaveToHistory (WPF Справочник по неуправляемым API)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: SaveToHistory
api_location: PresentationHost_v0400.dll
ms.assetid: 6dd101a3-44ad-4143-b228-772156f9b8ff
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b30884433f81aa5e4bf1241ae4fe34494bef788e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="b16a7-102">Функция SaveToHistory (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="b16a7-102">SaveToHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="b16a7-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="b16a7-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="b16a7-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления windows.</span><span class="sxs-lookup"><span data-stu-id="b16a7-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b16a7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b16a7-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b16a7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b16a7-106">Parameters</span></span>  
 <span data-ttu-id="b16a7-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="b16a7-107">pHistoryStream</span></span>  
 <span data-ttu-id="b16a7-108">Указатель на поток журнала.</span><span class="sxs-lookup"><span data-stu-id="b16a7-108">A pointer to the history stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b16a7-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b16a7-109">Requirements</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b16a7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b16a7-110">Requirements</span></span>  
 <span data-ttu-id="b16a7-111">**Платформы:** разделе [требования к системе для .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b16a7-111">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b16a7-112">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="b16a7-112">**DLL:**</span></span>  
  
 <span data-ttu-id="b16a7-113">В платформе .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="b16a7-113">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="b16a7-114">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="b16a7-114">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="b16a7-115">**Версия платформы .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b16a7-115">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b16a7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b16a7-116">See Also</span></span>  
 [<span data-ttu-id="b16a7-117">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="b16a7-117">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
