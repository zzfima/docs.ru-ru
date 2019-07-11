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
ms.openlocfilehash: ec18d5d5a6574cb0e08a6c4d6eaedcbcbf6886cd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759361"
---
# <a name="fusioninstallreference-structure"></a><span data-ttu-id="dcab0-102">Структура FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="dcab0-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="dcab0-103">Представляет ссылку, когда приложение устанавливает для сборки, приложение, установленной в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="dcab0-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcab0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dcab0-104">Syntax</span></span>  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="dcab0-105">Участники</span><span class="sxs-lookup"><span data-stu-id="dcab0-105">Members</span></span>  
  
|<span data-ttu-id="dcab0-106">Член</span><span class="sxs-lookup"><span data-stu-id="dcab0-106">Member</span></span>|<span data-ttu-id="dcab0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dcab0-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="dcab0-108">Размер структуры в байтах.</span><span class="sxs-lookup"><span data-stu-id="dcab0-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="dcab0-109">Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="dcab0-109">Reserved for future extensibility.</span></span> <span data-ttu-id="dcab0-110">Это значение должно быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="dcab0-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="dcab0-111">Добавляет ссылку на сущность.</span><span class="sxs-lookup"><span data-stu-id="dcab0-111">The entity that adds the reference.</span></span> <span data-ttu-id="dcab0-112">Это поле может иметь одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="dcab0-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="dcab0-113">-FUSION_REFCOUNT_MSI_GUID: Ссылка на сборку в приложении, был установлен с помощью установщика Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="dcab0-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="dcab0-114">`szIdentifier` Полю присваивается `MSI`и `szNonCanonicalData` поля задается значение `Windows Installer`.</span><span class="sxs-lookup"><span data-stu-id="dcab0-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="dcab0-115">Эта схема используется для сборок side-by-side Windows.</span><span class="sxs-lookup"><span data-stu-id="dcab0-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="dcab0-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: Ссылка на сборку приложением, которое отображается в **Add/Remove Programs** интерфейс.</span><span class="sxs-lookup"><span data-stu-id="dcab0-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="dcab0-117">`szIdentifier` Поле предоставляет маркер, который регистрирует приложение с **Add/Remove Programs** интерфейс.</span><span class="sxs-lookup"><span data-stu-id="dcab0-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="dcab0-118">-FUSION_REFCOUNT_FILEPATH_GUID: Ссылка на сборку приложением, которое представляется с помощью файла в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="dcab0-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="dcab0-119">`szIdentifier` Поле предоставляет путь к этому файлу.</span><span class="sxs-lookup"><span data-stu-id="dcab0-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="dcab0-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: Приложение, которое представлено только непрозрачная строка ссылается на сборку.</span><span class="sxs-lookup"><span data-stu-id="dcab0-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="dcab0-121">`szIdentifier` Поле предоставляет это непрозрачная строка.</span><span class="sxs-lookup"><span data-stu-id="dcab0-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="dcab0-122">Глобальный кэш сборок не проверяет наличие непрозрачных ссылок при удалении этого значения.</span><span class="sxs-lookup"><span data-stu-id="dcab0-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="dcab0-123">-FUSION_REFCOUNT_OSINSTALL_GUID: Это значение зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="dcab0-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="dcab0-124">Уникальная строка, определяющая приложения, которые установить сборки в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="dcab0-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="dcab0-125">Его значение зависит от значения `guidScheme` поля.</span><span class="sxs-lookup"><span data-stu-id="dcab0-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="dcab0-126">Строка, которая может интерпретировать только сущность, которая добавляет ссылку.</span><span class="sxs-lookup"><span data-stu-id="dcab0-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="dcab0-127">Глобальный кэш сборок сохраняет полученную строку, но не использует его.</span><span class="sxs-lookup"><span data-stu-id="dcab0-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dcab0-128">Требования</span><span class="sxs-lookup"><span data-stu-id="dcab0-128">Requirements</span></span>  
 <span data-ttu-id="dcab0-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcab0-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcab0-130">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="dcab0-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="dcab0-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcab0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcab0-132">См. также</span><span class="sxs-lookup"><span data-stu-id="dcab0-132">See also</span></span>

- [<span data-ttu-id="dcab0-133">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="dcab0-133">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [<span data-ttu-id="dcab0-134">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="dcab0-134">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
