---
title: Метод ICLRRuntimeInfo::GetVersionString
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b18323644220ffdce1caad966b8a0c2a7baddde2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrruntimeinfogetversionstring-method"></a>Метод ICLRRuntimeInfo::GetVersionString
Возвращает общий язык среды выполнения (CLR) сведения о версии данной [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейса.  
  
 Этот метод заменяет следующие функции:  
  
-   [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
  
-   [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pwzBuffer`  
 [out] Версии платформы .NET Framework компиляции, в формате «v*A*. *B*[. *X*]». *Объект*, *B*, и *X* — десятичные числа, соответствуют основной номер версии, дополнительный номер версии и номер сборки. *X* является необязательным. Если *X* — не существует, отсутствует конечная точка не.  
  
> [!NOTE]
>  Этот параметр должно соответствовать имени каталога для версии платформы .NET Framework, как оно отображается в разделе C:\Windows\Microsoft.NET\Framework.  
  
 Примеры значений: «v1.0.3705», «v1.1.4322», «v2.0.50727» и «v4.0. *x*», где *x* зависит от номера установленного построения. Обратите внимание, что префикс «v» является обязательным.  
  
 `pchBuffer`  
 [in, out] Указывает размер `pwzBuffer` для предотвращения переполнения буфера. Если `pwzBuffer` — `null`, `pchBuffer` возвращает требуемый размер `pwzBuffer` чтобы разрешить предварительное выделение.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|`pwzBuffer` или `pchBuffer` равно null.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
