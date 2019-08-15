---
title: Функция LoadTypeLibWithResolver
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b9bec757071a98e085ccdeee3fc66bfc07f52bc
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040165"
---
# <a name="loadtypelibwithresolver-function"></a>Функция LoadTypeLibWithResolver
Загружает библиотеку типов и использует предоставляемый [интерфейс итипелибресолвер](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) для разрешения любых библиотек типов, на которые имеются ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a>Параметры  
 `szFile`  
 окне Путь к файлу библиотеки типов.  
  
 `regkind`  
 окне Флаг [перечисления регкинд](https://docs.microsoft.com/windows/win32/api/oleauto/ne-oleauto-regkind) , управляющий регистрацией библиотеки типов. Возможные значения:  
  
- `REGKIND_DEFAULT`: Использовать поведение регистрации по умолчанию.  
  
- `REGKIND_REGISTER`: Зарегистрируйте эту библиотеку типов.  
  
- `REGKIND_NONE`: Не регистрировать эту библиотеку типов.  
  
 `pTlbResolver`  
 окне Указатель на реализацию [интерфейса итипелибресолвер](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).  
  
 `pptlib`  
 заполняет Ссылка на загружаемую библиотеку типов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Одно из значений HRESULT, перечисленных в следующей таблице.  
  
|Возвращаемое значение|Значение|  
|------------------|-------------|  
|`S_OK`|Выполнено.|  
|`E_OUTOFMEMORY`|Недостаточно памяти.|  
|`E_POINTER`|Один или несколько указателей являются недопустимыми.|  
|`E_INVALIDARG`|Один или несколько аргументов являются недопустимыми.|  
|`TYPE_E_IOERROR`|Функции не удалось выполнить запись в файл.|  
|`TYPE_E_REGISTRYACCESS`|Не удалось открыть базу данных регистрации системы.|  
|`TYPE_E_INVALIDSTATE`|Не удалось открыть библиотеку типов.|  
|`TYPE_E_CANTLOADLIBRARY`|Не удалось загрузить библиотеку типов или библиотеку DLL.|  
  
## <a name="remarks"></a>Примечания  
 [Программа Tlbexp. exe (средство экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) вызывает `LoadTypeLibWithResolver` функцию во время преобразования сборки в библиотеку типов.  
  
 Эта функция загружает указанную библиотеку типов с минимальным доступом к реестру. Затем функция проверяет библиотеку типов для внутренних ссылочных библиотек типов, каждая из которых должна быть загружена и добавлена в родительскую библиотеку типов.  
  
 Прежде чем можно будет загрузить библиотеку типов, на которую указывает ссылка, путь к файлу ссылки должен быть разрешаться в полный путь к файлу. Это осуществляется с помощью [метода ресолветипелиб](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) , предоставляемого [интерфейсом итипелибресолвер](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), который `pTlbResolver` передается в параметре.  
  
 Если известен полный путь к файлу библиотеки типов, на которую указывает ссылка, `LoadTypeLibWithResolver` функция загружает и добавляет библиотеку типов, на которую указывает ссылка, в родительскую библиотеку типов, создавая объединенную библиотеку типов Master.  
  
 После того как функция разрешает и загружает все библиотеки типов, на которые имеются ссылки, она возвращает ссылку на библиотеку разрешенных шаблонов в `pptlib` параметре.  
  
 Функция обычно вызывается программой [Tlbexp. exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), которая предоставляет собственную внутреннюю реализацию `pTlbResolver` [интерфейса итипелибресолвер](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) в параметре. `LoadTypeLibWithResolver`  
  
 При вызове `LoadTypeLibWithResolver` напрямую необходимо предоставить собственную реализацию [интерфейса итипелибресолвер](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Тлбреф. h  
  
 **Библиотечная** Тлбреф. lib  
  
 **Версия .NET Framework:** 3,5, 3,0, 2,0  
  
## <a name="see-also"></a>См. также

- [Вспомогательные функции Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [Функция Лоадтипелибекс](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
