---
title: Функция LoadLibraryShim
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c8936fa3d22cfde4c2536fccf9d46c1990133db1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445316"
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="3746a-102">Функция LoadLibraryShim</span><span class="sxs-lookup"><span data-stu-id="3746a-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="3746a-103">Загружает заданную версию библиотеки DLL, которая включается в распространяемый пакет платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3746a-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="3746a-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3746a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="3746a-105">Используйте [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="3746a-105">Use the [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3746a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3746a-106">Syntax</span></span>  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3746a-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="3746a-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="3746a-108">[in] Нулем строка, представляющая имя библиотеки DLL, загружаемой библиотеки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3746a-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="3746a-109">[in] Нулем строка, представляющая версию библиотеки DLL для загрузки.</span><span class="sxs-lookup"><span data-stu-id="3746a-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="3746a-110">Если `szVersion` равен null, выбранной для загрузки последней версии, указанной библиотеки DLL, которая меньше, чем версия 4 версии.</span><span class="sxs-lookup"><span data-stu-id="3746a-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="3746a-111">То есть, все версии меньше, чем версия 4 учитываются, если `szVersion` имеет значение null, и если установлен без версии меньше, чем версии 4, не загружается.</span><span class="sxs-lookup"><span data-stu-id="3746a-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="3746a-112">Это гарантирует, что установка [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] не влияет на существующие приложения или компоненты.</span><span class="sxs-lookup"><span data-stu-id="3746a-112">This is to ensure that installation of the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] does not affect pre-existing applications or components.</span></span> <span data-ttu-id="3746a-113">См. в записи [SxS незавершенного и быстрый запуск миграции](http://go.microsoft.com/fwlink/?LinkId=200329) в блоге команды среды CLR.</span><span class="sxs-lookup"><span data-stu-id="3746a-113">See the entry [In-Proc SxS and Migration Quick Start](http://go.microsoft.com/fwlink/?LinkId=200329) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="3746a-114">Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="3746a-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="3746a-115">[out] Указатель на дескриптор модуля.</span><span class="sxs-lookup"><span data-stu-id="3746a-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3746a-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3746a-116">Return Value</span></span>  
 <span data-ttu-id="3746a-117">Этот метод возвращает стандартные коды ошибок модели объектов компонентов (COM), как определено в файле WinError.h, кроме следующих значений.</span><span class="sxs-lookup"><span data-stu-id="3746a-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="3746a-118">Код возврата</span><span class="sxs-lookup"><span data-stu-id="3746a-118">Return code</span></span>|<span data-ttu-id="3746a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="3746a-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3746a-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="3746a-120">S_OK</span></span>|<span data-ttu-id="3746a-121">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="3746a-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="3746a-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="3746a-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="3746a-123">Загрузка `szDllName` требует загрузки не удается загрузить необходимую версию среды CLR и общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="3746a-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3746a-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="3746a-124">Remarks</span></span>  
 <span data-ttu-id="3746a-125">Эта функция используется для загрузки библиотек DLL, включенных в распространяемый пакет платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3746a-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="3746a-126">Она не загружает библиотеки DLL, созданного пользователем.</span><span class="sxs-lookup"><span data-stu-id="3746a-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3746a-127">Начиная с .NET Framework версии 2.0, загрузка Fusion.dll среда CLR для загрузки.</span><span class="sxs-lookup"><span data-stu-id="3746a-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="3746a-128">Это так, как функции в Fusion.dll теперь являются оболочками, в реализации которых предоставляются средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="3746a-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3746a-129">Требования</span><span class="sxs-lookup"><span data-stu-id="3746a-129">Requirements</span></span>  
 <span data-ttu-id="3746a-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3746a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3746a-131">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3746a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3746a-132">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3746a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3746a-133">См. также</span><span class="sxs-lookup"><span data-stu-id="3746a-133">See Also</span></span>  
 [<span data-ttu-id="3746a-134">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="3746a-134">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
