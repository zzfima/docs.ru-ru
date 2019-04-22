---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: eb84e0a7038e7ff8cb399ac7222b6ac1661b5bc1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842165"
---
# <a name="-optimize"></a>-optimize
Включает или отключает оптимизацию компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательный параметр. `-optimize-` Отключает оптимизацию компилятора. `-optimize+` Включает оптимизацию. По умолчанию оптимизация отключена.|  
  
## <a name="remarks"></a>Примечания  
 Оптимизации компилятора делают код более быстрым, коротким и эффективным. Тем не менее, так как оптимизации изменения порядка строк кода в выходном файле `-optimize+` может осложнить процесс отладки.  
  
 Все модули, созданные с помощью `-target:module` для сборки, должны использовать одинаковые `-optimize` параметры сборки. Дополнительные сведения см. в разделе [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 Вы можете объединить `-optimize` и `-debug` параметры.  
  
|Чтобы задать - оптимизации в среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.<br />     <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно** .<br />4.  Изменить **включить оптимизацию** "флажок".|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и включает оптимизацию.  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
