---
title: "Перечисление COINITIEE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COINITIEE
api_location: mscoree.dll
api_type: COM
f1_keywords: COINITIEE
helpviewer_keywords: COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad117c3efd31cc176281e571b7fde11229c097e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="dabab-102">Перечисление COINITIEE</span><span class="sxs-lookup"><span data-stu-id="dabab-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="dabab-103">Указывает константы, используемые [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) при инициализации общеязыковая среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="dabab-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dabab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dabab-104">Syntax</span></span>  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="dabab-105">Участники</span><span class="sxs-lookup"><span data-stu-id="dabab-105">Members</span></span>  
  
|<span data-ttu-id="dabab-106">Член</span><span class="sxs-lookup"><span data-stu-id="dabab-106">Member</span></span>|<span data-ttu-id="dabab-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="dabab-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="dabab-108">Режим инициализации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dabab-108">Default initialization mode.</span></span> <span data-ttu-id="dabab-109">Это Инициализирует среду выполнения и создает по умолчанию <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="dabab-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="dabab-110">Выполняет инициализацию для запуска управляемой библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="dabab-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="dabab-111">Выполняет инициализацию для запуска управляемого EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="dabab-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="dabab-112">Инициализирует среду выполнения, но не создает значение по умолчанию <xref:System.AppDomain>, который создается после входа в основную процедуру EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="dabab-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dabab-113">Требования</span><span class="sxs-lookup"><span data-stu-id="dabab-113">Requirements</span></span>  
 <span data-ttu-id="dabab-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dabab-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dabab-115">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dabab-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dabab-116">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dabab-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dabab-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dabab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dabab-118">См. также</span><span class="sxs-lookup"><span data-stu-id="dabab-118">See Also</span></span>  
 [<span data-ttu-id="dabab-119">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="dabab-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
