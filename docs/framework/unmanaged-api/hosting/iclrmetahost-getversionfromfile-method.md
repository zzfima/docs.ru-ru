---
title: "Метод ICLRMetaHost::GetVersionFromFile"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.GetVersionFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90fcf5ca8306c4e91ff6b96bac36ad2639d81d5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostgetversionfromfile-method"></a>Метод ICLRMetaHost::GetVersionFromFile
Получает сборки исходной версии платформы .NET Framework компиляции (хранятся в метаданных), по его пути файла. Этот метод заменяет [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pwzFilePath`  
 [in] Путь к файлу завершения сборки.  
  
 `pwzbuffer`  
 [out] Версии платформы .NET Framework компиляции, хранятся в метаданных в формате «v*A*. *B*[. *X*]». *Объект*, *B*, и *X* — десятичные числа, соответствуют основной номер версии, дополнительный номер версии и номер сборки. Длина этой строки ограничена MAX_PATH.  
  
> [!NOTE]
>  Этот выход совпадает имя каталога для версии платформы .NET Framework, она появится в разделе C:\Windows\Microsoft.NET\Framework.  
  
 Примеры значений: «v1.0.3705», «v1.1.4322», «v2.0.50727» и «v4.0. *X*», где *X* зависит от номера установленного построения. Обратите внимание, что префикс «v» является обязательным.  
  
 `pcchBuffer`  
 [in, out] Размер `pwzbuffer` для предотвращения переполнения буфера.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|`pwzbuffer` или `pcchBuffer` равно null.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|Размер буфера слишком мал.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICLRMetaHost-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
