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
ms.openlocfilehash: 3a6da0e845fa50d090cdf0808b211a5806c40961
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178218"
---
# <a name="_corvalidateimage-function"></a>Функция _CorValidateImage
Проверяет управляемые изображения модулей и уведомляет загрузчик операционной системы после их загрузки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ImageBase`  
 (в) Указатель на исходное местоположение изображения для проверки в виде управляемого кода. Изображение уже должно быть загружено в память.  
  
 `FileName`  
 (в) Имя файла изображения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Эта функция возвращает стандартные `E_OUTOFMEMORY` `E_UNEXPECTED` `E_FAIL` `E_INVALIDARG`значения, и, а также следующие значения.  
  
|Возвращаемое значение|Описание|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|Изображение недействительно. Это значение имеет HRESULT 0xC000007BL.|  
|`STATUS_SUCCESS`|Изображение действительно. Это значение имеет HRESULT 0x0000000L.|  
  
## <a name="remarks"></a>Remarks  
 В Windows XP и более поздних версиях загрузчик операционной системы проверяет управляемые модули, изучая бит каталога com Descriptor в общем формате файла объекта (COFF). Набор бита указывает на управляемый модуль. Если погрузчик обнаруживает управляемый модуль, он загружает MsCorEE.dll и вызывает, `_CorValidateImage`который выполняет следующие действия:  
  
- Подтверждает, что изображение является действительным управляемым модулем.  
  
- Изменяет точку входа в изображении на точку входа в время выполнения общего языка (CLR).  
  
- Для 64-битных версий Windows изменяет изображение, накотороговое в памяти, преобразовывая его из формата PE32 в формат PE32.  
  
- Возвращается к погрузчику при загрузке управляемых изображений модуля.  
  
 Для исполняемых изображений загрузчик операционной системы вызывает [функцию _CorExeMain,](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) независимо от точки входа, указанной в исполняемой. Для сборки DLL-изображений погрузчик вызывает [функцию _CorDllMain.](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
  
 `_CorExeMain`или `_CorDllMain` выполняет следующие действия:  
  
- Инициализирует CLR.  
  
- Находит управляемую точку входа от заголовка CLR сборки.  
  
- Начинает исполнение.  
  
 Погрузчик вызывает [функцию _CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) при разгрузке управляемых изображений модуля. Однако эта функция не выполняет никаких действий; он просто возвращается.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Глобальные статические функции метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
