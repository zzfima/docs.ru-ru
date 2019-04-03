---
title: Значение типа <typename1> невозможно привести к <typename2>
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: 5f313a43bc3a2f983dabbd45477d120fdb80d063
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829031"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a>Значение типа "\<Имя_типа1 >" нельзя преобразовать в "\<имя_типа2 >"
Значение типа "\<Имя_типа1 >" нельзя преобразовать в "\<имя_типа2 >". Несоответствие типов может быть вызвана смешением ссылки на файл в проект ссылку на сборку "\<имя_сборки >". Попробуйте заменить ссылку на файл "\<filepath >" в проекте "\<имя_проекта1 >" со ссылкой проекта "\<имя_проекта2 >".  
  
 В ситуации, когда проект делает ссылку на проект и ссылку на файл компилятор не может гарантировать, что один тип может быть преобразован в другой.  
  
 Следующий псевдокод иллюстрирует ситуацию, которая может вызвать эту ошибку.  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 Проект `P1` делает косвенную ссылку проекта через проект `P2` проект `P3`, а также прямые ссылки на файл `P3`. Объявление `commonObject` использует ссылку на файл `P3`, тогда как вызов `P2.getCommonClass` использует ссылку на проект `P3`.  
  
 В этой ситуации проблема в том, что ссылка на файл задает путь к файлу и имя выходного файла `P3` (обычно p3.dll), хотя в проект ссылку на определение исходного проекта (`P3`) по имени проекта. По этой причине компилятор не может гарантировать, что тип `P3.commonClass` поступает из того же исходного кода через две различные ссылки.  
  
 Такая ситуация обычно возникает, когда ссылка проекта и используются переменные типов ссылок на файлы. В предыдущем примере, может не происходить, если `P1` сделать прямую ссылку проекта на `P3` вместо ссылки на файл.  
  
 **Идентификатор ошибки:** BC30955  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Измените ссылку на файл для ссылки на проект.  
  
## <a name="see-also"></a>См. также

- [Преобразование типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)
