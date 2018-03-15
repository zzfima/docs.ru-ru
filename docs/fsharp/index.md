---
title: "Руководство по языку F#"
description: "Это руководство предоставляет обзор различных учебных материалов для языка F #, это функциональный язык программирования, работающей на платформе .NET."
author: jackfoxy
ms.author: phcart
ms.date: 02/28/2018
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: b7cf3feb5699f85bf09a47f008fdaf70ac7c8d77
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="f-guide"></a>Руководство по языку F#

F # — функциональной язык программирования, который выполняется на платформе .NET. Он также имеет полную поддержку для объектов, позволяя функциональной blend и программирование объекта прагматичное использование решения проблемы.

```fsharp
open System // Get access to functionality in System namespace.

// Function: takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

// Use the EntryPoint attribute to run the program.
[<EntryPoint>]
let main args =
    args                     // Use F# pipe operators to send the args into some functions.
    |> Array.map getGreeting // Turn each name into a friendly greeting.
    |> Array.iter printfn    // Print them!

    0
```

F # — о производительности сущность. Поддержка инструментами F # является универсальной, так и полного дополнительных возможностей.

## <a name="learning-f"></a>Изучение F # #

[Учебник по F #](tour.md) предоставляет обзор функций основной язык с большим количеством примеров кода. Рекомендуется, если впервые введены в F # и чтобы понять, как работает язык.

[Начало работы с F # в Visual Studio](get-started/get-started-visual-studio.md) Если вы используете Windows и полное взаимодействие IDE Visual Studio (среда разработки Integraded).

[Начало работы с F # в Visual Studio для Mac](get-started/get-started-with-visual-studio-for-mac.md) при работе на macOS и хотите использовать Visual Studio IDE.

[Начало работы с F # в Visual Studio Code](get-started/get-started-vscode.md) Если требуется компактное между различными платформами и возникают упакованные функции интегрированной среды разработки.

[Начало работы с F # с .NET Core CLI](get-started/get-started-command-line.md) Если требуется использование средств командной строки.

## <a name="references"></a>Ссылки

[Справочник по языку F #](language-reference/index.md) является официальным и полную ссылку для всех компонентов языка F #. Каждой статьи о синтаксисе и примеры кода. В оглавлении можно использовать панель фильтра для поиска конкретных статей.

[Справочник по основной библиотеке F #](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) является Справочник по API для основной библиотеки F #.

## <a name="additional-guides"></a>Дополнительные руководства

[F # для удовольствия и прибыли](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) книга в очень подробные на изучение F #. Его содержимое и автор любимое сообществом F #. Целевая аудитория — в первую очередь разработчики объектно-ориентированного программирования фоне.

[Wikibook программирования F #](https://en.wikibooks.org/wiki/F_Sharp_Programming) является wikibook обучения F #. Это также продукта сообщества F #. Целевая аудитория — людей, которые являются новыми в F #, с небольшим фона объектно-ориентированного программирования.

## <a name="learn-f-through-videos"></a>Сведения о F # видео

[Учебник по F # на YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) , отлично сведения о F # с помощью Visual Studio, показывающая большое количество демонстрации в ходе 1,5 часа. Целевая аудитория — Visual Studio разработчиков, незнакомых с F #.

[Введение в программирование на F #](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) является отличным серии видеороликов, использует в качестве основной редактор кода Visual Studio. Серия видеоматериалов начинается с nothing и заканчивается Создание текстовых RPG игру. Целевая аудитория — разработчиков, которые предпочитают кода Visual Studio (или упрощенных IDE) и не знакомы с F #.

[Новые возможности Visual Studio 2017 г. для F # для разработчиков](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) видео курс, в котором представлены некоторые новые функции для языка F # в Visual Studio 2017 г. Целевая аудитория — Visual Studio разработчиков, незнакомых с F #.

## <a name="other-useful-resources"></a>Другие полезные ресурсы

[Веб-сайта для F # фрагменты](http://www.fssnip.net) содержит набор больших фрагментов кода в F #, — от начинающих до высокой Дополнительно фрагменты практически что угодно.

[Slack Foundation программного обеспечения F #](http://fsharp.org/guides/slack/) — отличное место для начинающих и экспертов одинаково, высокой активностью и обладает некоторыми мире наиболее F # программистов для разговора. Корпорация Майкрософт рекомендует присоединения.

## <a name="the-f-software-foundation"></a>F# Software Foundation

Несмотря на то, что Майкрософт является основным разработчиком его средства в Visual Studio и языке F #, F # также поддерживаемый независимых foundation, F # программного обеспечения Foundation (FSSF).

В задачи F# Software Foundation входит продвижение, защита и совершенствование языка программирования F#, а также поддержка и расширение международного сообщества программистов F#.

Узнать дополнительные сведения и принять участие в этой работе можно на сайте [fsharp.org](http://fsharp.org). Он распространяется бесплатно присоединить и сеть разработчиков F # в foundation является то, что вы не хотите пропустите!