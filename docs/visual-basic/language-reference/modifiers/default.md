---
title: Default
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: ad4c9528f208cc2c31f07b0506d1b049a7568c86
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351584"
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
Определяет свойство как свойство по умолчанию для класса, структуры или интерфейса.  
  
## <a name="remarks"></a>Заметки  
 Класс, структура или интерфейс могут обозначать не более одного из своих свойств как *свойство по умолчанию*, если это свойство принимает по крайней мере один параметр. Если код создает ссылку на класс или структуру без указания члена, Visual Basic разрешает эту ссылку на свойство по умолчанию.  
  
 Свойства по умолчанию могут привести к небольшому сокращению количества символов в исходном коде, но они могут усложнить чтение кода. Если вызывающий код не знаком с классом или структурой, то при создании ссылки на имя класса или структуры он не может определить, обращается ли эта ссылка к самому классу или структуре, или к свойству по умолчанию. Это может привести к ошибкам компилятора или незначительным логическим ошибкам времени выполнения.  
  
 Можно немного уменьшить вероятность ошибок свойств по умолчанию, всегда используя [оператор Option строго](../../../visual-basic/language-reference/statements/option-strict-statement.md) , чтобы установить проверку типа компилятора на `On`.  
  
 Если вы планируете использовать в коде предопределенный класс или структуру, необходимо определить, имеет ли он свойство по умолчанию, и, если да, то, какое имя имеет значение.  
  
 Из-за этих недостатков рекомендуется не определять свойства по умолчанию. Для удобочитаемости кода следует также рассмотреть возможность явной ссылки на все свойства, даже свойства по умолчанию.  
  
 Модификатор `Default` можно использовать в этом контексте:  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>См. также

- [Инструкции. объявление и вызов свойства по умолчанию в Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
