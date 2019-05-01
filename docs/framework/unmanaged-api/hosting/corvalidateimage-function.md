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
ms.openlocfilehash: df9cc0cc86237b1ec439a4ec4fa6a75429c416d9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985781"
---
# <a name="corvalidateimage-function"></a>Функция _CorValidateImage
Проверяет образы управляемого модуля и уведомляет загрузчик операционной системы, после они были загружены.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ImageBase`  
 [in] Указатель на начальное расположение образа для проверки, как управляемый код. Изображение уже должен быть загружен в память.  
  
 `FileName`  
 [in] Имя файла изображения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Эта функция возвращает стандартные значения `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, и `E_FAIL`, а также следующие значения.  
  
|Возвращаемое значение|Описание|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|Недопустимый образ. Это значение имеет HRESULT 0xC000007BL.|  
|`STATUS_SUCCESS`|Образ является допустимым. Это значение имеет HRESULT 0x00000000L.|  
  
## <a name="remarks"></a>Примечания  
 В Windows XP и более поздних версий загрузчик операционной системы ищет управляемые модули, проверяя бит каталога дескриптора модели COM в заголовке формате COFF файл общего объекта. Установленный бит обозначает управляемый модуль. При обнаружении управляемый модуль, он загружает библиотеку MsCorEE.dll и вызывает метод `_CorValidateImage`, который выполняет следующие действия:  
  
- Подтверждает, что образ является допустимым управляемым модулем.  
  
- Заменяет точку входа в образе на точку входа в системе common language runtime (CLR).  
  
- Для 64-разрядных версиях Windows изменяет образ, находящийся в памяти, путем преобразования его из формата PE32 в формат PE32 +.  
  
- Возвращает загрузчику при загрузке образов управляемого модуля.  
  
 Для исполняемых образов загрузчик операционной системы затем вызывает [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) функции, независимо от точки входа, указанной в исполняемом файле. Библиотеки DLL сборки образов, загрузчик вызывает [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) функции.  
  
 `_CorExeMain` или `_CorDllMain` выполняет следующие действия:  
  
- Инициализирует среду CLR.  
  
- Находит управляемую точку входа в заголовке среды CLR сборки.  
  
- Начинает выполнение.  
  
 Вызовы загрузчика [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) функционировать, когда управляемые образы модулей будут выгружены. Тем не менее эта функция не выполняет никаких действий; он просто возвращает.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
