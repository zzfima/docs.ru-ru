---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: e9ef32912c2afb3c99e46e1e14bb3daa5a2e99af
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005709"
---
# <a name="getcustomui"></a>GetCustomUI
Вызывается PresentationHost. exe для получения настраиваемого хода выполнения и сообщений об ошибках с узла, если они реализованы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzProgressAssemblyName`  
  
 заполняет Указатель на сборку, содержащую пользовательский интерфейс хода выполнения.  
  
 `pwzProgressClassName`  
  
 заполняет Имя класса, предоставляемого ведущим пользовательским интерфейсом выполнения, предпочтительнее XAML-файл с <xref:System.Windows.Controls.Page> является элементом верхнего уровня. Этот класс находится в сборке, заданной `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 заполняет Указатель на сборку, содержащую пользовательский интерфейс ошибки, предоставляемый узлом.  
  
 `pwzErrorClassName`  
  
 заполняет Имя класса, предоставляемого ведущим пользовательским интерфейсом ошибок, предпочтительный XAML-файл с <xref:System.Windows.Controls.Page> является элементом верхнего уровня. Этот класс находится в сборке, заданной `pwzErrorAssemblyName`.  
  
## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 HRESULT: игнорируется.  
  
## <a name="remarks"></a>Примечания  
 Ведущее приложение может иметь определенную тему, которая может не соответствовать интерфейсу пользователя PresentationHost. exe по умолчанию. В этом случае ведущее приложение может реализовать [GetCustomUI](getcustomui.md) для возврата сведений о ходе выполнения и ошибок пользовательского интерфейса в PresentationHost. exe. PresentationHost. exe всегда будет вызывать [GetCustomUI](getcustomui.md) перед использованием пользовательских интерфейсов по умолчанию.  
  
 Эта функция вызывается один раз во время инициализации PresentationHost.  
  
## <a name="see-also"></a>См. также:

- [IWpfHostSupport](iwpfhostsupport.md)
