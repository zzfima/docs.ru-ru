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
ms.openlocfilehash: b4d0ad0c8651fe10bd2a1c72a8a995846cc80a55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440782"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="76056-102">Перечисление COINITIEE</span><span class="sxs-lookup"><span data-stu-id="76056-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="76056-103">Указывает константы, используемые [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) при инициализации общеязыковая среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="76056-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76056-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76056-104">Syntax</span></span>  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="76056-105">Участники</span><span class="sxs-lookup"><span data-stu-id="76056-105">Members</span></span>  
  
|<span data-ttu-id="76056-106">Член</span><span class="sxs-lookup"><span data-stu-id="76056-106">Member</span></span>|<span data-ttu-id="76056-107">Описание</span><span class="sxs-lookup"><span data-stu-id="76056-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="76056-108">Режим инициализации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="76056-108">Default initialization mode.</span></span> <span data-ttu-id="76056-109">Это Инициализирует среду выполнения и создает по умолчанию <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="76056-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="76056-110">Выполняет инициализацию для запуска управляемой библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="76056-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="76056-111">Выполняет инициализацию для запуска управляемого EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="76056-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="76056-112">Инициализирует среду выполнения, но не создает значение по умолчанию <xref:System.AppDomain>, который создается после входа в основную процедуру EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="76056-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76056-113">Требования</span><span class="sxs-lookup"><span data-stu-id="76056-113">Requirements</span></span>  
 <span data-ttu-id="76056-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76056-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76056-115">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="76056-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="76056-116">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76056-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="76056-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76056-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76056-118">См. также</span><span class="sxs-lookup"><span data-stu-id="76056-118">See Also</span></span>  
 [<span data-ttu-id="76056-119">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="76056-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
