---
title: Функция _CorValidateImage
ms.date: 03/30/2017
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 101271823f7b7877bb7f007588b6a164233e5b45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="corvalidateimage-function"></a>Функция _CorValidateImage
Проверяет образы управляемого модуля и уведомляет загрузчик операционной системы после их загрузки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ImageBase`  
 [in] Указатель начальной позиции образа для проверки, как управляемый код. Изображение уже должны быть загружены в память.  
  
 `FileName`  
 [in] Имя файла изображения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Эта функция возвращает стандартные значения `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, и `E_FAIL`, а также следующие значения.  
  
|Возвращаемое значение|Описание|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|Недопустимый образ. Это значение имеет HRESULT 0xC000007BL.|  
|`STATUS_SUCCESS`|Образ является допустимым. Это значение имеет HRESULT 0x00000000L.|  
  
## <a name="remarks"></a>Примечания  
 В Windows XP и более поздних версиях загрузчик операционной системы выполняет поиск управляемых модулей путем анализа бит каталога дескриптора модели COM в заголовке общего формата (COFF) объекта файла. Установленный бит обозначает управляемый модуль. При обнаружении управляемый модуль, он загружает MsCorEE.dll и вызывает метод `_CorValidateImage`, который выполняет следующие действия:  
  
-   Подтверждает, что образ является допустимым управляемым модулем.  
  
-   Заменяет точку входа в образе на точку входа в общеязыковой среде выполнения (CLR).  
  
-   Для 64-разрядных версиях Windows изменяет образ, находящийся в памяти, путем преобразования его из формата PE32 в формат PE32 +.  
  
-   Возврат загрузчик при загрузке образов управляемого модуля.  
  
 Для исполняемых образов загрузчик операционной системы затем вызывает [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) функции, независимо от точки входа, указанной в исполняемом файле. Библиотека DLL сборки образов, загрузчик вызывает [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) функции.  
  
 `_CorExeMain` или `_CorDllMain` выполняет следующие действия:  
  
-   Инициализирует среду CLR.  
  
-   Находит управляемую точку входа в заголовке CLR сборки.  
  
-   Начинает выполнение.  
  
 Вызовы загрузчика [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) работать при управлении образов модуля будут выгружены. Однако эта функция не выполняет никаких действий; он просто возвращает.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Глобальные статические функции метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
