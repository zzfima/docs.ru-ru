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
ms.openlocfilehash: 9ab44ce8f51620d83084d1dd16e98b2b310feb76
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968940"
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="79649-102">Функция LoadLibraryShim</span><span class="sxs-lookup"><span data-stu-id="79649-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="79649-103">Загружает указанную версию библиотеки DLL, которая входит в состав распространяемого пакета .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="79649-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="79649-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="79649-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="79649-105">Используйте вместо этого метод [ICLRRuntimeInfo:: LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) .</span><span class="sxs-lookup"><span data-stu-id="79649-105">Use the [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79649-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79649-106">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79649-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="79649-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="79649-108">окне Строка, завершающаяся нулем, которая представляет имя библиотеки DLL, загружаемой из библиотеки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="79649-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="79649-109">окне Строка, заканчивающаяся нулем и представляющая версию загружаемой библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="79649-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="79649-110">Если `szVersion` параметр имеет значение null, версия, выбранная для загрузки, является последней версией указанной библиотеки DLL, которая меньше версии 4.</span><span class="sxs-lookup"><span data-stu-id="79649-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="79649-111">То есть все версии, равные или больше версии 4, игнорируются, `szVersion` если имеет значение null, и если не установлена версия, отличная от версии 4, то не удается загрузить библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="79649-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="79649-112">Это необходимо для того, чтобы установка .NET Framework 4 не влияла на существующие приложения или компоненты.</span><span class="sxs-lookup"><span data-stu-id="79649-112">This is to ensure that installation of the .NET Framework 4 does not affect pre-existing applications or components.</span></span> <span data-ttu-id="79649-113">См. запись [In-Proc SxS и Migration быстрое начало](https://go.microsoft.com/fwlink/?LinkId=200329) в блоге команды разработчиков CLR.</span><span class="sxs-lookup"><span data-stu-id="79649-113">See the entry [In-Proc SxS and Migration Quick Start](https://go.microsoft.com/fwlink/?LinkId=200329) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="79649-114">Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="79649-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="79649-115">заполняет Указатель на маркер модуля.</span><span class="sxs-lookup"><span data-stu-id="79649-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79649-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="79649-116">Return Value</span></span>  
 <span data-ttu-id="79649-117">Этот метод возвращает коды стандартных ошибок модели COM, как определено в файле WinError. h, в дополнение к следующим значениям.</span><span class="sxs-lookup"><span data-stu-id="79649-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="79649-118">Код возврата</span><span class="sxs-lookup"><span data-stu-id="79649-118">Return code</span></span>|<span data-ttu-id="79649-119">Описание</span><span class="sxs-lookup"><span data-stu-id="79649-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="79649-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="79649-120">S_OK</span></span>|<span data-ttu-id="79649-121">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="79649-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="79649-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="79649-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="79649-123">Для `szDllName` загрузки требуется загрузка среды CLR, и необходимая версия CLR не может быть загружена.</span><span class="sxs-lookup"><span data-stu-id="79649-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79649-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="79649-124">Remarks</span></span>  
 <span data-ttu-id="79649-125">Эта функция используется для загрузки библиотек DLL, включенных в распространяемый пакет .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="79649-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="79649-126">Он не загружает создаваемые пользователем библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="79649-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="79649-127">Начиная с версии .NET Framework 2,0, Загрузка Fusion. dll приводит к загрузке среды CLR.</span><span class="sxs-lookup"><span data-stu-id="79649-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="79649-128">Это обусловлено тем, что функции в Fusion. dll теперь являются оболочками, реализации которых предоставляются средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="79649-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79649-129">Требования</span><span class="sxs-lookup"><span data-stu-id="79649-129">Requirements</span></span>  
 <span data-ttu-id="79649-130">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79649-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79649-131">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="79649-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="79649-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79649-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79649-133">См. также</span><span class="sxs-lookup"><span data-stu-id="79649-133">See also</span></span>

- [<span data-ttu-id="79649-134">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="79649-134">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
