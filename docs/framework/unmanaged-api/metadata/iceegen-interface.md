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
ms.openlocfilehash: 0e3e70749a768377ea470bc44a66b9fdabbb1f93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iceegen-interface"></a>Интерфейс ICeeGen
Предоставляет методы для динамической компиляции кода.  
  
 Этот интерфейс устарел и не должны использоваться.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|Является устаревшей. Добавляет инструкцию .reloc в базу кода.|  
|[Метод AllocateMethodBuffer](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|Является устаревшей. Создает буфер указанного размера для метода и получает относительный виртуальный адрес метода.|  
|[Метод ComputePointer](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|Является устаревшей. Определяет буфер для заданного раздела кода.|  
|[Метод EmitString](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|Является устаревшей. Выдает заданную строку в базу кода.|  
|[Метод GenerateCeeFile](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Является устаревшей. Создает файл базы кода, содержащий базу кода, загруженных в этот момент `ICeeGen`.|  
|[Метод GenerateCeeMemoryImage](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Является устаревшей. Создает образ в памяти в базе кода.|  
|[Метод GetIlSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Является устаревшей. Получает раздел базовый код на промежуточном языке ссылается заданный дескриптор.|  
|[Метод GetIMapTokenIface](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Является устаревшей. Возвращает интерфейс, который ссылается указанный токен.|  
|[Метод GetMethodBuffer](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Является устаревшей. Получает буфер соответствующего размера в указанный относительный виртуальный адрес метода.|  
|[Метод GetSectionBlock](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Является устаревшей. Получает блок базы кода раздела.|  
|[Метод GetSectionCreate](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Является устаревшей. Создает и возвращает раздел кода с помощью указанного имени и значения флагов.|  
|[Метод GetSectionDataLen](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Является устаревшей. Получает длину указанного раздела.|  
|[Метод GetString](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Является устаревшей. Возвращает строку, хранящуюся по указанному относительному виртуальному адресу.|  
|[Метод GetStringSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Является устаревшей. Возвращает строковое представление раздела кода, который ссылается указанный дескриптор.|  
|[Метод TruncateSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Является устаревшей. Усекает заданный раздел кода указанной длины.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
