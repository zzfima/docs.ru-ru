---
title: Модульное тестирование в .NET Core и .NET Standard
description: В этой статье представлен краткий обзор модульного тестирования для проектов .NET Core и .NET Standard.
author: ardalis
ms.author: wiwagn
ms.date: 08/30/2017
ms.custom: seodec18
ms.openlocfilehash: ad02cf9eefafd3711ccf654e23f075a00f035e2a
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "74551832"
---
# <a name="unit-testing-in-net-core-and-net-standard"></a>Модульное тестирование в .NET Core и .NET Standard

.NET Core позволяет легко создавать модульные тесты. В этой статье рассматриваются модульные тесты и то, чем они отличаются от других типов тестов. В связанных ресурсах в нижней части страницы содержится информация о том, как добавить тестовый проект в решение. После настройки тестового проекта вы сможете запустить модульные тесты в командной строке или Visual Studio.

Сведения о тестировании проекта **ASP.NET Core** см. в статье [Интеграционные тесты в ASP.NET Core](/aspnet/core/test/integration-tests#test-app-prerequisites).

.NET Core 2.0 и более поздней версии поддерживает платформу [.NET Standard 2.0](../../standard/net-standard.md). Для демонстрации модульных тестов будут использоваться ее библиотеки.

Вы можете использовать встроенные шаблоны проектов .NET Core 2.0 и более поздних версий для C#, F# и Visual Basic, чтобы создать свой проект.

## <a name="what-are-unit-tests"></a>Что такое модульные тесты?

Наличие автоматических тестов — отличный способ обеспечить работу приложения именно так, как она задумывалась разработчиками. Существует несколько типов тестов для программных приложений. Они включают интеграционные тесты, веб-тесты, нагрузочные тесты и другие. **Модульные тесты** проверяют отдельные компоненты и методы программного обеспечения. Модульные тесты должны проверять только код, к которому у разработчика есть доступ. Они не должны затрагивать инфраструктуру. Инфраструктура включает базы данных, файловые системы и сетевые ресурсы. 

Также обратите внимание, что для написания тестов есть рекомендации. Например, [разработка на основе тестирования](https://deviq.com/test-driven-development/) выполняется, когда модульный тест написан до кода, который ему нужно проверить. Разработка на основе тестирования похожа на план книги. Она помогает разработчикам писать более простой, удобочитаемый и эффективный код. 

> [!NOTE]
> Команда ASP.NET следует [этим соглашениям](https://github.com/aspnet/Home/wiki/Engineering-guidelines#unit-tests-and-functional-tests), чтобы разработчики могли придумать понятные имена тестовых классов и методов.

Попробуйте не создавать зависимости в инфраструктуре при написании модульных тестов. Из-за этого тесты выполняются медленно и нестабильно. Зависимости следует использовать в интеграционных тестах. Чтобы избежать появления зависимостей в коде приложения, следуйте [принципу явных зависимостей](https://deviq.com/explicit-dependencies-principle/) и используйте [внедрение зависимостей](/aspnet/core/fundamentals/dependency-injection). Вы также можете разместить модульные тесты в отдельном проекте, не содержащем интеграционных тестов. Это гарантирует отсутствие в проекте модульного теста ссылок на пакеты инфраструктуры или зависимостей от них.

## <a name="next-steps"></a>Следующие шаги

Дополнительные сведения о модульном тестировании в проектах .NET Core.

Проекты модульных тестов .NET Core поддерживаются для следующих языков:

- [C#](../../csharp/index.yml)
- [F#](../../fsharp/index.yml)
- [Visual Basic](../../visual-basic/index.md) 

Также вы можете выбрать один из следующих вариантов:

- [xUnit](https://xunit.github.io) 
- [NUnit](https://nunit.org)
- [MSTest](https://github.com/Microsoft/testfx-docs)

Дополнительные сведения см. в следующих пошаговых руководствах:

- Создание модульных тестов с помощью [*xUnit*, *C#* и .NET Core CLI](unit-testing-with-dotnet-test.md).
- Создание модульных тестов с помощью [*NUnit*, *C#* и интерфейса командной строки .NET Core](unit-testing-with-nunit.md).
- Создание модульных тестов с помощью [*MSTest*, *C#* и .NET Core CLI](unit-testing-with-mstest.md).
- Создание модульных тестов с помощью [*xUnit*, *F#* и .NET Core CLI](unit-testing-fsharp-with-dotnet-test.md).
- Создание модульных тестов с помощью [*NUnit*, *F#* и интерфейса командной строки .NET Core](unit-testing-fsharp-with-nunit.md).
- Создание модульных тестов с помощью [*MSTest*, *F#* и .NET Core CLI](unit-testing-fsharp-with-mstest.md).
- Создание модульных тестов с помощью [*xUnit*, *Visual Basic* и .NET Core CLI](unit-testing-visual-basic-with-dotnet-test.md).
- Создание модульных тестов с помощью [*NUnit*, *Visual Basic* и интерфейса командной строки .NET Core](unit-testing-visual-basic-with-nunit.md).
- Создание модульных тестов с помощью [*MSTest*, *Visual Basic* и .NET Core CLI](unit-testing-visual-basic-with-mstest.md).

Дополнительные сведения см. в следующих статьях:

- Visual Studio Enterprise предлагает отличные средства тестирования для .NET Core. Дополнительные сведения: [Live Unit Testing](/visualstudio/test/live-unit-testing) и [Code Coverage](https://github.com/Microsoft/vstest-docs/blob/master/docs/analyze.md#working-with-code-coverage).
- Дополнительные сведения о выборочном модульном тестировании см. в разделах [Выполнение выборочных модульных тестов](selective-unit-tests.md) и [Включение и исключение тестов с помощью Visual Studio](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods).
- [Как использовать xUnit с .NET Core и Visual Studio](https://xunit.github.io/docs/getting-started-dotnet-core.html).
