---
title: Структура FUSION_INSTALL_REFERENCE
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4685d1a23fdf1874817522a16ccd428d81acd1ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fusioninstallreference-structure"></a><span data-ttu-id="777df-102">Структура FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="777df-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="777df-103">Представляет ссылку, когда приложение устанавливает на сборку, установленную приложением в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="777df-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="777df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="777df-104">Syntax</span></span>  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="777df-105">Участники</span><span class="sxs-lookup"><span data-stu-id="777df-105">Members</span></span>  
  
|<span data-ttu-id="777df-106">Член</span><span class="sxs-lookup"><span data-stu-id="777df-106">Member</span></span>|<span data-ttu-id="777df-107">Описание</span><span class="sxs-lookup"><span data-stu-id="777df-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="777df-108">Размер структуры в байтах.</span><span class="sxs-lookup"><span data-stu-id="777df-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="777df-109">Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="777df-109">Reserved for future extensibility.</span></span> <span data-ttu-id="777df-110">Это значение должно быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="777df-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="777df-111">Сущность, которая добавляет ссылку.</span><span class="sxs-lookup"><span data-stu-id="777df-111">The entity that adds the reference.</span></span> <span data-ttu-id="777df-112">Это поле может принимать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="777df-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="777df-113">-FUSION_REFCOUNT_MSI_GUID: Ссылку на сборку приложения, установленного с помощью установщика Windows.</span><span class="sxs-lookup"><span data-stu-id="777df-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="777df-114">`szIdentifier` Имеет значение `MSI`и `szNonCanonicalData` имеет значение `Windows Installer`.</span><span class="sxs-lookup"><span data-stu-id="777df-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="777df-115">Эта схема используется для сборок Windows side-by-side.</span><span class="sxs-lookup"><span data-stu-id="777df-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="777df-116">-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: Ссылку на сборку приложения, которое отображается в **Установка и удаление программ** интерфейса.</span><span class="sxs-lookup"><span data-stu-id="777df-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="777df-117">`szIdentifier` Поле предоставляет маркер, регистрирующий приложение с **Установка и удаление программ** интерфейса.</span><span class="sxs-lookup"><span data-stu-id="777df-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="777df-118">-FUSION_REFCOUNT_FILEPATH_GUID: Ссылку на сборку приложения, которое представляется с помощью файла в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="777df-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="777df-119">`szIdentifier` Поле предоставляет путь к этому файлу.</span><span class="sxs-lookup"><span data-stu-id="777df-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="777df-120">-FUSION_REFCOUNT_OPAQUE_STRING_GUID: Ссылку на сборку приложения, представленного только непрозрачная строка.</span><span class="sxs-lookup"><span data-stu-id="777df-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="777df-121">`szIdentifier` Поле предоставляет это непрозрачная строка.</span><span class="sxs-lookup"><span data-stu-id="777df-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="777df-122">Глобальный кэш сборок не проверяет наличие непрозрачных ссылок при удалении этого значения.</span><span class="sxs-lookup"><span data-stu-id="777df-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="777df-123">-FUSION_REFCOUNT_OSINSTALL_GUID: Это значение зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="777df-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="777df-124">Уникальная строка, идентифицирующая приложения, которая установлена сборка в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="777df-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="777df-125">Его значение зависит от значения `guidScheme` поля.</span><span class="sxs-lookup"><span data-stu-id="777df-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="777df-126">Строка, которая может интерпретировать только сущность, которая добавляет ссылку.</span><span class="sxs-lookup"><span data-stu-id="777df-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="777df-127">Глобальный кэш сборок эта строка хранится, но не используется.</span><span class="sxs-lookup"><span data-stu-id="777df-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="777df-128">Требования</span><span class="sxs-lookup"><span data-stu-id="777df-128">Requirements</span></span>  
 <span data-ttu-id="777df-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="777df-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="777df-130">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="777df-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="777df-131">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="777df-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="777df-132">См. также</span><span class="sxs-lookup"><span data-stu-id="777df-132">See Also</span></span>  
 [<span data-ttu-id="777df-133">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="777df-133">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="777df-134">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="777df-134">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
