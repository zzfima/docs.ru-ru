---
title: Переменная использует неподдерживаемый тип автоматизации
ms.date: 07/20/2015
f1_keywords:
- vbrID458
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
ms.openlocfilehash: 944c0c63cd0d7ae7f9ff770fd123231464af1eaf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344832"
---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a>Переменная использует тип автоматизации, не поддерживаемый в Visual Basic

Предпринята попытка использовать переменную, определенную в библиотеке типов или библиотеке объектов, которая имеет тип данных, не поддерживаемый Visual Basic.

## <a name="to-correct-this-error"></a>Исправление ошибки

- Используйте переменную типа, распознаваемый Visual Basic.

     -или-

- Если эта ошибка возникает при использовании `FileGet` или `FileGetObject`, убедитесь, что файл, который вы пытаетесь использовать, записан с помощью `FilePut` или `FilePutObject`.

## <a name="see-also"></a>См. также:

- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
