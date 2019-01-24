---
title: Интерфейс ICeeGen
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c5dadbe757464b24ef532fdd8abe5457fa995348
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555067"
---
# <a name="iceegen-interface"></a>Интерфейс ICeeGen
Предоставляет методы для динамической компиляции кода.  
  
 Этот интерфейс является устаревшим и не должны использоваться.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|Является устаревшей. Добавляет инструкцию .reloc базы кода.|  
|[Метод AllocateMethodBuffer](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|Является устаревшей. Создает буфер заданного размера для метода и возвращает относительный виртуальный адрес метода.|  
|[Метод ComputePointer](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|Является устаревшей. Определяет буфер для заданного раздела кода.|  
|[Метод EmitString](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|Является устаревшей. Создает указанную строку в базу кода.|  
|[Метод GenerateCeeFile](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Является устаревшей. Создает файл базы кода, который содержит базу кода, загруженные в этот момент `ICeeGen`.|  
|[Метод GenerateCeeMemoryImage](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Является устаревшей. Формирует изображение в памяти для базы кода.|  
|[Метод GetIlSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Является устаревшей. Получает раздел базовый код на промежуточном языке ссылается заданный дескриптор.|  
|[Метод GetIMapTokenIface](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Является устаревшей. Получает интерфейс, который ссылается указанный токен.|  
|[Метод GetMethodBuffer](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Является устаревшей. Получает буфер соответствующего размера в указанный относительный виртуальный адрес метода.|  
|[Метод GetSectionBlock](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Является устаревшей. Получает блок разделе базы кода.|  
|[Метод GetSectionCreate](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Является устаревшей. Создает и возвращает раздел кода, используя указанные имя и значения флагов.|  
|[Метод GetSectionDataLen](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Является устаревшей. Получает длину указанного раздела.|  
|[Метод GetString](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Является устаревшей. Получает строку, хранящуюся в указанный относительный виртуальный адрес.|  
|[Метод GetStringSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Является устаревшей. Получает строковое представление раздела кода, который ссылается указанный дескриптор.|  
|[Метод TruncateSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Является устаревшей. Усекает заданный раздел кода указанной длины.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
