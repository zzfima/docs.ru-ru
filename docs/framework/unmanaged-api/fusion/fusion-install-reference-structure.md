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
ms.openlocfilehash: 9e81fb7c99b9fd03a69456a84f2191770f40121d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795344"
---
# <a name="fusion_install_reference-structure"></a><span data-ttu-id="6c2b7-102">Структура FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="6c2b7-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="6c2b7-103">Представляет ссылку, которую приложение делает с сборкой, установленной приложением в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c2b7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c2b7-104">Syntax</span></span>  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="6c2b7-105">Участники</span><span class="sxs-lookup"><span data-stu-id="6c2b7-105">Members</span></span>  
  
|<span data-ttu-id="6c2b7-106">Член</span><span class="sxs-lookup"><span data-stu-id="6c2b7-106">Member</span></span>|<span data-ttu-id="6c2b7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6c2b7-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="6c2b7-108">Размер структуры в байтах.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="6c2b7-109">Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-109">Reserved for future extensibility.</span></span> <span data-ttu-id="6c2b7-110">Это значение должно быть равно 0 (нулю).</span><span class="sxs-lookup"><span data-stu-id="6c2b7-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="6c2b7-111">Сущность, которая добавляет ссылку.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-111">The entity that adds the reference.</span></span> <span data-ttu-id="6c2b7-112">Это поле может иметь одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="6c2b7-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="6c2b7-113">- FUSION_REFCOUNT_MSI_GUID: На сборку ссылается приложение, установленное с помощью установщик Windows Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="6c2b7-114">Поле имеет `szNonCanonicalData` значение, а поле имеет значение `Windows Installer`. `MSI` `szIdentifier`</span><span class="sxs-lookup"><span data-stu-id="6c2b7-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="6c2b7-115">Эта схема используется для параллельных сборок Windows.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="6c2b7-116">- FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: На сборку ссылается приложение, которое отображается в интерфейсе " **Установка и удаление программ** ".</span><span class="sxs-lookup"><span data-stu-id="6c2b7-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="6c2b7-117">Поле предоставляет маркер, регистрирующий приложение с помощью интерфейса « **Установка и удаление программ».** `szIdentifier`</span><span class="sxs-lookup"><span data-stu-id="6c2b7-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="6c2b7-118">- FUSION_REFCOUNT_FILEPATH_GUID: На сборку ссылается приложение, представленное файлом в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="6c2b7-119">`szIdentifier` Поле предоставляет путь к этому файлу.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="6c2b7-120">- FUSION_REFCOUNT_OPAQUE_STRING_GUID: На сборку ссылается приложение, представленное только непрозрачной строкой.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="6c2b7-121">`szIdentifier` Поле предоставляет эту непрозрачную строку.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="6c2b7-122">Глобальный кэш сборок не проверяет наличие непрозрачных ссылок при удалении этого значения.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="6c2b7-123">- FUSION_REFCOUNT_OSINSTALL_GUID: Это значение зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="6c2b7-124">Уникальная строка, идентифицирующая приложение, которое установило сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="6c2b7-125">Его значение зависит от значения `guidScheme` поля.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="6c2b7-126">Строка, понятная только сущности, которая добавляет ссылку.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="6c2b7-127">Глобальный кэш сборок хранит эту строку, но не использует ее.</span><span class="sxs-lookup"><span data-stu-id="6c2b7-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c2b7-128">Требования</span><span class="sxs-lookup"><span data-stu-id="6c2b7-128">Requirements</span></span>  
 <span data-ttu-id="6c2b7-129">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c2b7-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c2b7-130">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="6c2b7-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6c2b7-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c2b7-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c2b7-132">См. также</span><span class="sxs-lookup"><span data-stu-id="6c2b7-132">See also</span></span>

- [<span data-ttu-id="6c2b7-133">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="6c2b7-133">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="6c2b7-134">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="6c2b7-134">Global Assembly Cache</span></span>](../../app-domains/gac.md)
