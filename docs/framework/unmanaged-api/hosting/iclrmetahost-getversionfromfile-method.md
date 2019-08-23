---
title: Метод ICLRMetaHost::GetVersionFromFile
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd5d2e820bd1d733bb4ab968a89174124bc91357
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962941"
---
# <a name="iclrmetahostgetversionfromfile-method"></a>Метод ICLRMetaHost::GetVersionFromFile
Возвращает исходную версию компиляции .NET Framework сборки (хранящейся в метаданных) по указанному пути к файлу. Этот метод заменяет функцию [жетфилеверсион](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzFilePath`  
 окне Полный путь к файлу сборки.  
  
 `pwzbuffer`  
 заполняет Версия компиляции .NET Framework, хранящаяся в метаданных, в формате "v*A*. *Б* [. *X*] ". *A*, *B*и *X* — это десятичные числа, соответствующие основной версии, дополнительной версии и номеру сборки. Длина этой строки ограничена MAX_PATH.  
  
> [!NOTE]
> Эти выходные данные соответствуют имени каталога для .NET Framework версии, как отображается в разделе К:\виндовс\микрософт.нет\фрамеворк.  
  
 Примеры значений: "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" и "v 4.0. *X*", где *X* зависит от установленного номера сборки. Обратите внимание, что требуется префикс "v".  
  
 `pcchBuffer`  
 [вход, выход] Размер `pwzbuffer` во избежание переполнения буфера.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|`pwzbuffer` или `pcchBuffer` равно null.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|Буфер слишком мал.|  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Метахост. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
