---
title: Перечисление AssemblyRefFlags
ms.date: 03/30/2017
api_name:
- AssemblyRefFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyRefFlags
helpviewer_keywords:
- AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type:
- apiref
ms.openlocfilehash: 23d293a87112c62cb2127b435faeca258a7de226
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444225"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="c50c7-102">Перечисление AssemblyRefFlags</span><span class="sxs-lookup"><span data-stu-id="c50c7-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="c50c7-103">Содержит значения, описывающие функции ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="c50c7-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c50c7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c50c7-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c50c7-105">Члены</span><span class="sxs-lookup"><span data-stu-id="c50c7-105">Members</span></span>  
  
|<span data-ttu-id="c50c7-106">Член</span><span class="sxs-lookup"><span data-stu-id="c50c7-106">Member</span></span>|<span data-ttu-id="c50c7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c50c7-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="c50c7-108">Указывает, что ссылка на сборку содержит полные нехэшированные сведения об издателе сборки.</span><span class="sxs-lookup"><span data-stu-id="c50c7-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c50c7-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c50c7-109">Requirements</span></span>  
 <span data-ttu-id="c50c7-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c50c7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c50c7-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c50c7-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c50c7-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c50c7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c50c7-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c50c7-113">See also</span></span>

- [<span data-ttu-id="c50c7-114">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="c50c7-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="c50c7-115">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="c50c7-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="c50c7-116">Метод DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="c50c7-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
