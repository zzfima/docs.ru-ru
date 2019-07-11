---
title: Функция CreateVersionStringFromModule
ms.date: 03/30/2017
api_name:
- CreateVersionStringFromModule
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CreateVersionStringFromModule
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CreateVersionStringFromModule function
ms.assetid: 3d2fe9bd-75ef-4364-84a6-da1e1994ac1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b68624b962ed610dbeecd3e4cead769ab1400f4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739209"
---
# <a name="createversionstringfrommodule-function"></a>Функция CreateVersionStringFromModule
Создает строку версии из пути среды CLR в целевом процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateVersionStringFromModule (  
    [in]  DWORD      pidDebuggee,  
    [in]  LPCWSTR    szModuleName,  
    [out, size_is(cchBuffer),  
          length_is(*pdwLength)] LPWSTR Buffer,  
    [in]  DWORD      cchBuffer,  
    [out] DWORD*     pdwLength  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pidDebuggee`  
 [in] Идентификатор процесса, в котором загружается целевая среды CLR.  
  
 `szModuleName`  
 [in] Полный или относительный путь к целевой среде CLR, которая загружается в процесс.  
  
 `pBuffer`  
 [out] Буфер возврата для хранения строки версии целевой среды CLR.  
  
 `cchBuffer`  
 [in] Размер `pBuffer`.  
  
 `pdwLength`  
 [out] Длина строки версии, возвращенной `pBuffer`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Строка версии для целевой среды CLR успешно возвращена в `pBuffer`.  
  
 E_INVALIDARG  
 Параметр `szModuleName` имеет значение null, либо один из параметров `pBuffer` и `cchBuffer` имеет значение null. Оба параметра `pBuffer` и `cchBuffer` должны иметь значение null или не иметь значение null.  
  
 HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)  
 Значение `pdwLength` больше значения `cchBuffer`. Это может быть ожидаемым результатом, если вы передали значение null в оба параметра  `pBuffer` и `cchBuffer`, а также запросили необходимый размер буфера с помощью `pdwLength`.  
  
 HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)  
 Параметр `szModuleName` не содержит путь к допустимой среде CLR в целевом процессе.  
  
 E_FAIL (или другие коды возврата E_)  
 Параметр `pidDebuggee` не ссылается на допустимый процесс, или произошел другой сбой.  
  
## <a name="remarks"></a>Примечания  
 Эта функция принимает процесс CLR, который определяется параметром `pidDebuggee` и строкой пути, заданной параметром `szModuleName`. Строка версии возвращается в буфер, на который указывает `pBuffer`. Эта строка непрозрачна для пользователя функции, то есть сама строка версии не имеет внутреннего смысла. Он используется исключительно в контексте этой функции и [функция CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md).  
  
 Эта функция должна вызываться дважды. При первом вызове передайте значение null для обоих параметров `pBuffer` и `cchBuffer`. После этого размер буфера, необходимый для `pBuffer`, будет возвращен в `pdwLength`. Затем можно вызвать эту функцию во второй раз и передать буфер в `pBuffer` и его размер в `cchBuffer`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** dbgshim.h  
  
 **Библиотека:** dbgshim.dll  
  
 **Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)
