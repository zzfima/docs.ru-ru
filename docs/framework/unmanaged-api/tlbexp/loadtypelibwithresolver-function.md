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
ms.openlocfilehash: 5d2f5ad2afb2e73acead82369782f142aa10aac3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782712"
---
# <a name="loadtypelibwithresolver-function"></a>Функция LoadTypeLibWithResolver
Загружает библиотеку типов и использует предоставленный [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) для разрешения любых типов, на которые библиотек.  
  
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
 [in] Путь к файлу библиотеки типов.  
  
 `regkind`  
 [in] Объект [REGKIND перечисления](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) флаг, который определяет, как библиотека типов зарегистрирована. Его возможными значениями являются:  
  
- `REGKIND_DEFAULT`: Используйте поведение по умолчанию регистрации.  
  
- `REGKIND_REGISTER`: Регистрации этой библиотеки типов.  
  
- `REGKIND_NONE`: Не Регистрируйте этой библиотеки типов.  
  
 `pTlbResolver`  
 [in] Указатель на реализацию [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).  
  
 `pptlib`  
 [out] Ссылка на библиотеку типов, который загружается.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Одно из значений HRESULT, перечисленных в следующей таблице.  
  
|Возвращаемое значение|Значение|  
|------------------|-------------|  
|`S_OK`|Выполнено.|  
|`E_OUTOFMEMORY`|Недостаточно памяти.|  
|`E_POINTER`|Один или несколько указателей являются недопустимыми.|  
|`E_INVALIDARG`|Один или несколько аргументов являются недопустимыми.|  
|`TYPE_E_IOERROR`|Функция не удалось записать в файл.|  
|`TYPE_E_REGISTRYACCESS`|Не удалось открыть системную базу данных регистрации.|  
|`TYPE_E_INVALIDSTATE`|Не удалось открыть библиотеку типов.|  
|`TYPE_E_CANTLOADLIBRARY`|Не удается загрузить библиотеку типов или библиотеку DLL.|  
  
## <a name="remarks"></a>Примечания  
 [Tlbexp.exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) вызовы `LoadTypeLibWithResolver` функции во время преобразования сборки для типа библиотеки.  
  
 Эта функция загружает указанной библиотеки типов с минимальным доступом к реестру. Затем функция проверяет библиотеку типов для библиотеки типов, на которые, каждый из которых необходимо загрузить и добавить в библиотеку типов родительского.  
  
 Прежде чем можно загрузить библиотеку типов, на которую указывает ссылка, пути к файлу ссылки должны разрешаться в полный путь к файлу. Это обеспечивается за счет [метод ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) , предоставляемая [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), который передается в `pTlbResolver` параметра.  
  
 Если известно, полный путь к файлу библиотеки типов, на которую указывает ссылка, `LoadTypeLibWithResolver` функция загружает и добавляет эту библиотеку в родительскую библиотеку типов, Создание объединенного главную библиотеку типов.  
  
 После того как функция разрешает и загружает все библиотеки типов, на которые, он возвращает ссылку на библиотеку master разрешенный тип в `pptlib` параметра.  
  
 `LoadTypeLibWithResolver` Обычно вызывается функция [Tlbexp.exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), который предоставляет свой собственный внутренний [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) реализации в `pTlbResolver` параметр.  
  
 При вызове метода `LoadTypeLibWithResolver` напрямую, необходимо создать собственные [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) реализации.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** TlbRef.h  
  
 **Библиотека:** TlbRef.lib  
  
 **Версии платформы .NET framework:** 3.5, 3.0, 2.0  
  
## <a name="see-also"></a>См. также

- [Вспомогательные функции Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [Функция LoadTypeLibEx](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
