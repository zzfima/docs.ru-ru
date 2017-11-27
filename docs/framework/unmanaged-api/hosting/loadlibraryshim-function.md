---
title: "Функция LoadLibraryShim"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: LoadLibraryShim
helpviewer_keywords: LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c56f5a3576c505fd7b7d514e3f2d038e7f8f3ecc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="5d859-102">Функция LoadLibraryShim</span><span class="sxs-lookup"><span data-stu-id="5d859-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="5d859-103">Загружает заданную версию библиотеки DLL, которая включается в распространяемый пакет платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5d859-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="5d859-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d859-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="5d859-105">Используйте [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="5d859-105">Use the [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d859-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d859-106">Syntax</span></span>  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d859-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d859-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="5d859-108">[in] Нулем строка, представляющая имя библиотеки DLL, загружаемой библиотеки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5d859-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="5d859-109">[in] Нулем строка, представляющая версию библиотеки DLL для загрузки.</span><span class="sxs-lookup"><span data-stu-id="5d859-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="5d859-110">Если `szVersion` равен null, выбранной для загрузки последней версии, указанной библиотеки DLL, которая меньше, чем версия 4 версии.</span><span class="sxs-lookup"><span data-stu-id="5d859-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="5d859-111">То есть, все версии меньше, чем версия 4 учитываются, если `szVersion` имеет значение null, и если установлен без версии меньше, чем версии 4, не загружается.</span><span class="sxs-lookup"><span data-stu-id="5d859-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="5d859-112">Это гарантирует, что установка [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] не влияет на существующие приложения или компоненты.</span><span class="sxs-lookup"><span data-stu-id="5d859-112">This is to ensure that installation of the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] does not affect pre-existing applications or components.</span></span> <span data-ttu-id="5d859-113">См. в записи [SxS незавершенного и быстрый запуск миграции](http://go.microsoft.com/fwlink/?LinkId=200329) в блоге команды среды CLR.</span><span class="sxs-lookup"><span data-stu-id="5d859-113">See the entry [In-Proc SxS and Migration Quick Start](http://go.microsoft.com/fwlink/?LinkId=200329) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="5d859-114">Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="5d859-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="5d859-115">[out] Указатель на дескриптор модуля.</span><span class="sxs-lookup"><span data-stu-id="5d859-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d859-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5d859-116">Return Value</span></span>  
 <span data-ttu-id="5d859-117">Этот метод возвращает стандартные коды ошибок модели объектов компонентов (COM), как определено в файле WinError.h, кроме следующих значений.</span><span class="sxs-lookup"><span data-stu-id="5d859-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="5d859-118">Код возврата</span><span class="sxs-lookup"><span data-stu-id="5d859-118">Return code</span></span>|<span data-ttu-id="5d859-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5d859-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5d859-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d859-120">S_OK</span></span>|<span data-ttu-id="5d859-121">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="5d859-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="5d859-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="5d859-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="5d859-123">Загрузка `szDllName` требует загрузки не удается загрузить необходимую версию среды CLR и общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="5d859-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d859-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d859-124">Remarks</span></span>  
 <span data-ttu-id="5d859-125">Эта функция используется для загрузки библиотек DLL, включенных в распространяемый пакет платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5d859-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="5d859-126">Она не загружает библиотеки DLL, созданного пользователем.</span><span class="sxs-lookup"><span data-stu-id="5d859-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d859-127">Начиная с .NET Framework версии 2.0, загрузка Fusion.dll среда CLR для загрузки.</span><span class="sxs-lookup"><span data-stu-id="5d859-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="5d859-128">Это так, как функции в Fusion.dll теперь являются оболочками, в реализации которых предоставляются средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="5d859-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d859-129">Требования</span><span class="sxs-lookup"><span data-stu-id="5d859-129">Requirements</span></span>  
 <span data-ttu-id="5d859-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d859-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d859-131">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d859-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d859-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d859-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d859-133">См. также</span><span class="sxs-lookup"><span data-stu-id="5d859-133">See Also</span></span>  
 [<span data-ttu-id="5d859-134">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="5d859-134">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
