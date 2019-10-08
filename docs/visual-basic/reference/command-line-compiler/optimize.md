---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: e8daf4a49123623b6470bc3c6281869f1b9b3d0f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005374"
---
# <a name="-optimize"></a>-optimize
Включает или отключает оптимизацию компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательный параметр. Параметр `-optimize-` отключает оптимизацию компилятора. Параметр `-optimize+` включает оптимизацию. По умолчанию оптимизация отключена.|  
  
## <a name="remarks"></a>Примечания  
 Оптимизации компилятора делают код более быстрым, коротким и эффективным. Однако поскольку оптимизация приводит к перестановке кода в выходном файле, `-optimize+` может усложнить отладку.  
  
 Все модули, созданные с `-target:module` для сборки, должны использовать те же параметры `-optimize`, что и сборка. Дополнительные сведения см. в разделе [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 Можно сочетать параметры `-optimize` и `-debug`.  
  
|Установка параметра-optimize в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.<br />     <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно** .<br />4.  Измените флажок **включить оптимизацию** .|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и включает оптимизацию компилятора.  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
