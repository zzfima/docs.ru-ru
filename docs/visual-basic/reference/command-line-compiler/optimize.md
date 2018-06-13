---
title: -Оптимизация
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: 2f066835c5f864538f281d4c58772e0e60c132f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649949"
---
# <a name="-optimize"></a>-Оптимизация
Включает или отключает оптимизацию компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательный. `-optimize-` Отключает оптимизацию компилятора. `-optimize+` Включает оптимизацию. По умолчанию оптимизация отключена.|  
  
## <a name="remarks"></a>Примечания  
 Оптимизации компилятора делают код более быстрым, коротким и эффективным. Тем не менее, поскольку оптимизации привести изменения порядка строк кода `-optimize+` может осложнить процесс отладки.  
  
 Все модули, созданные с помощью `-target:module` для сборки должны использовать одинаковые `-optimize` параметры сборки. Дополнительные сведения см. в разделе [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 Можно объединять `-optimize` и `-debug` параметры.  
  
|Чтобы задать - оптимизации в среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.<br />     <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно** .<br />4.  Изменить **включить оптимизацию** флажок.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и включает оптимизацию.  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
