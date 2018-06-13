---
title: Перечисление CorEventAttr
ms.date: 03/30/2017
api_name:
- CorEventAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorEventAttr
helpviewer_keywords:
- CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e4e4b9d9c7481bdc51aaf75b26b3805940875f8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442310"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="08218-102">Перечисление CorEventAttr</span><span class="sxs-lookup"><span data-stu-id="08218-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="08218-103">Содержит значения, описывающие метаданные события.</span><span class="sxs-lookup"><span data-stu-id="08218-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08218-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08218-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="08218-105">Участники</span><span class="sxs-lookup"><span data-stu-id="08218-105">Members</span></span>  
  
|<span data-ttu-id="08218-106">Член</span><span class="sxs-lookup"><span data-stu-id="08218-106">Member</span></span>|<span data-ttu-id="08218-107">Описание</span><span class="sxs-lookup"><span data-stu-id="08218-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="08218-108">Указывает, что событие является специальным и указывает его имя как.</span><span class="sxs-lookup"><span data-stu-id="08218-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="08218-109">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="08218-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="08218-110">Указывает, что общеязыковая среда выполнения должна проверять кодировку имени события.</span><span class="sxs-lookup"><span data-stu-id="08218-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="08218-111">Требования</span><span class="sxs-lookup"><span data-stu-id="08218-111">Requirements</span></span>  
 <span data-ttu-id="08218-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08218-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08218-113">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="08218-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="08218-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08218-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08218-115">См. также</span><span class="sxs-lookup"><span data-stu-id="08218-115">See Also</span></span>  
 [<span data-ttu-id="08218-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="08218-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
