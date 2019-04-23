---
title: Перечисление COINITIEE
ms.date: 03/30/2017
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4a84fdfdba96c58671302c723b8a56848b70eb60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180027"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="2206b-102">Перечисление COINITIEE</span><span class="sxs-lookup"><span data-stu-id="2206b-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="2206b-103">Задает константы, используемые [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) при инициализации среда CLR.</span><span class="sxs-lookup"><span data-stu-id="2206b-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2206b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2206b-104">Syntax</span></span>  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="2206b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2206b-105">Members</span></span>  
  
|<span data-ttu-id="2206b-106">Член</span><span class="sxs-lookup"><span data-stu-id="2206b-106">Member</span></span>|<span data-ttu-id="2206b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2206b-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="2206b-108">Режим инициализации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2206b-108">Default initialization mode.</span></span> <span data-ttu-id="2206b-109">Эта команда инициализирует среду выполнения и создает по умолчанию <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="2206b-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="2206b-110">Инициализирует для запуска управляемой библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="2206b-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="2206b-111">Инициализирует для запуска управляемого EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="2206b-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="2206b-112">Это Инициализирует среду выполнения, но не создает значение по умолчанию <xref:System.AppDomain>, который создается после входа в основную процедуру EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="2206b-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2206b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2206b-113">Requirements</span></span>  
 <span data-ttu-id="2206b-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2206b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2206b-115">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2206b-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2206b-116">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2206b-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2206b-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2206b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2206b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2206b-118">See also</span></span>

- [<span data-ttu-id="2206b-119">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="2206b-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
