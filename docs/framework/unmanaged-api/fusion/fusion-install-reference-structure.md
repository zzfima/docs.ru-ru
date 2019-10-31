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
ms.openlocfilehash: 3859752fd92a76f3fef1ceced0e792109b65106a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108278"
---
# <a name="fusion_install_reference-structure"></a><span data-ttu-id="98de9-102">Структура FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="98de9-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="98de9-103">Представляет ссылку, которую приложение делает с сборкой, установленной приложением в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="98de9-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98de9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98de9-104">Syntax</span></span>  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="98de9-105">Члены</span><span class="sxs-lookup"><span data-stu-id="98de9-105">Members</span></span>  
  
|<span data-ttu-id="98de9-106">Член</span><span class="sxs-lookup"><span data-stu-id="98de9-106">Member</span></span>|<span data-ttu-id="98de9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="98de9-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="98de9-108">Размер структуры в байтах.</span><span class="sxs-lookup"><span data-stu-id="98de9-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="98de9-109">Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="98de9-109">Reserved for future extensibility.</span></span> <span data-ttu-id="98de9-110">Это значение должно быть равно 0 (нулю).</span><span class="sxs-lookup"><span data-stu-id="98de9-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="98de9-111">Сущность, которая добавляет ссылку.</span><span class="sxs-lookup"><span data-stu-id="98de9-111">The entity that adds the reference.</span></span> <span data-ttu-id="98de9-112">Это поле может иметь одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="98de9-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="98de9-113">-FUSION_REFCOUNT_MSI_GUID. на сборку ссылается приложение, установленное с помощью установщик Windows Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="98de9-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="98de9-114">Для поля `szIdentifier` установлено значение `MSI`, а для поля `szNonCanonicalData` — значение `Windows Installer`.</span><span class="sxs-lookup"><span data-stu-id="98de9-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="98de9-115">Эта схема используется для параллельных сборок Windows.</span><span class="sxs-lookup"><span data-stu-id="98de9-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="98de9-116">-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID. на сборку ссылается приложение, которое отображается в интерфейсе " **Установка и удаление программ** ".</span><span class="sxs-lookup"><span data-stu-id="98de9-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="98de9-117">Поле `szIdentifier` предоставляет маркер, регистрирующий приложение с помощью интерфейса « **Установка и удаление программ** ».</span><span class="sxs-lookup"><span data-stu-id="98de9-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="98de9-118">-FUSION_REFCOUNT_FILEPATH_GUID. на сборку ссылается приложение, представленное файлом в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="98de9-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="98de9-119">Поле `szIdentifier` предоставляет путь к этому файлу.</span><span class="sxs-lookup"><span data-stu-id="98de9-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="98de9-120">-FUSION_REFCOUNT_OPAQUE_STRING_GUID: на сборку ссылается приложение, представленное только непрозрачной строкой.</span><span class="sxs-lookup"><span data-stu-id="98de9-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="98de9-121">Поле `szIdentifier` предоставляет эту непрозрачную строку.</span><span class="sxs-lookup"><span data-stu-id="98de9-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="98de9-122">Глобальный кэш сборок не проверяет наличие непрозрачных ссылок при удалении этого значения.</span><span class="sxs-lookup"><span data-stu-id="98de9-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="98de9-123">-FUSION_REFCOUNT_OSINSTALL_GUID: это значение зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="98de9-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="98de9-124">Уникальная строка, идентифицирующая приложение, которое установило сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="98de9-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="98de9-125">Его значение зависит от значения поля `guidScheme`.</span><span class="sxs-lookup"><span data-stu-id="98de9-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="98de9-126">Строка, понятная только сущности, которая добавляет ссылку.</span><span class="sxs-lookup"><span data-stu-id="98de9-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="98de9-127">Глобальный кэш сборок хранит эту строку, но не использует ее.</span><span class="sxs-lookup"><span data-stu-id="98de9-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98de9-128">Требования</span><span class="sxs-lookup"><span data-stu-id="98de9-128">Requirements</span></span>  
 <span data-ttu-id="98de9-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98de9-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98de9-130">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="98de9-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="98de9-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98de9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98de9-132">См. также</span><span class="sxs-lookup"><span data-stu-id="98de9-132">See also</span></span>

- [<span data-ttu-id="98de9-133">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="98de9-133">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="98de9-134">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="98de9-134">Global Assembly Cache</span></span>](../../app-domains/gac.md)
