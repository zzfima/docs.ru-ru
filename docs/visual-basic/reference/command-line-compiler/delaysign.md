---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 3ee94df096b756be544964cfbbd405355e3f728f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581272"
---
# <a name="-delaysign"></a>-delaysign

Указывает, будет ли сборка полностью или частично подписана.

## <a name="syntax"></a>Синтаксис

```console
-delaysign[+ | -]
```

## <a name="arguments"></a>Аргументы

`+` &#124; `-`  
Необязательный. Если требуется полностью подписанная сборка, используйте `-delaysign-`. Используйте `-delaysign+`, если требуется поместить открытый ключ в сборку и зарезервировать пространство для подписанного хэша. Значение по умолчанию: `-delaysign-`.

## <a name="remarks"></a>Заметки

Параметр `-delaysign` не действует, если не используется с [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) или [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).

При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом. Итоговая цифровая подпись хранится в файле, содержащем манифест. Если сборка имеет отложенную подпись, компилятор не выполняет вычисление и сохранение подписи, но резервирует место в файле, чтобы подпись могла быть добавлена позже.

Например, с помощью `-delaysign+` разработчик в Организации может распространять неподписанные тестовые версии сборки, которые тестеры могут зарегистрировать в глобальном кэше сборок и использовать. После завершения работы над сборкой лицо, ответственное за закрытый ключ Организации, может полностью подписать сборку. Этот обособление защищает закрытый ключ Организации от раскрытия, позволяя всем разработчикам работать с сборками.

Дополнительные сведения о подписывании сборки см. в разделе [Создание и использование сборок со строгими именами](../../../standard/assembly/create-use-strong-named.md) .

### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>Установка параметра-delaysign в интегрированной среде разработки Visual Studio

1. Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.

2. Откройте вкладку **Подписывание**.

3. Задайте значение в поле **только отложенная подпись** .

## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
