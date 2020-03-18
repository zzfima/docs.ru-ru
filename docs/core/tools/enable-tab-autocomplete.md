---
title: Включение автодополнения клавишей TAB
description: В этой статье объясняется, как включить автодополнение клавишей TAB для .NET Core CLI в средах PowerShell, Bash и zsh.
author: thraka
ms.author: adegeo
ms.date: 11/03/2019
ms.openlocfilehash: 31328be14811760bc8d7fb527e0d55abfe6b1493
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156755"
---
# <a name="how-to-enable-tab-completion-for-the-net-core-cli"></a><span data-ttu-id="2e728-103">Включение автодополнения клавишей TAB для .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="2e728-103">How to enable TAB completion for the .NET Core CLI</span></span>

<span data-ttu-id="2e728-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="2e728-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="2e728-105">В этой статье описывается, как включить автодополнение нажатием клавиши TAB для трех оболочек: PowerShell, Bash и zsh.</span><span class="sxs-lookup"><span data-stu-id="2e728-105">This article describes how to configure tab completion for three shells, PowerShell, Bash, and zsh.</span></span> <span data-ttu-id="2e728-106">Сведения о том, как настроить заполнение нажатием клавиши TAB в других оболочках, см. в соответствующей документации.</span><span class="sxs-lookup"><span data-stu-id="2e728-106">For other shells, refer to their documentation on how to configure tab completion.</span></span>

<span data-ttu-id="2e728-107">После настройки заполнение нажатием клавиши TAB для .NET Core CLI можно активировать, введя в командной строке `dotnet` и нажав клавишу TAB.</span><span class="sxs-lookup"><span data-stu-id="2e728-107">Once set up, tab completion for the .NET Core CLI is triggered by typing a `dotnet` command in the shell, and then pressing the TAB key.</span></span> <span data-ttu-id="2e728-108">Текущая командная строка будет передана команде `dotnet complete`, а оболочка обработает результаты.</span><span class="sxs-lookup"><span data-stu-id="2e728-108">The current command line is sent to the `dotnet complete` command, and the results are processed by your shell.</span></span> <span data-ttu-id="2e728-109">Вы можете проверить результаты без активации автодополнения клавишей TAB, передав что-либо непосредственно команде `dotnet complete`.</span><span class="sxs-lookup"><span data-stu-id="2e728-109">You can test the results without enabling tab completion by sending something directly to the `dotnet complete` command.</span></span> <span data-ttu-id="2e728-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="2e728-110">For example:</span></span>

```console
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

<span data-ttu-id="2e728-111">Если команда не сработала, убедитесь, что установлен пакет SDK для .NET Core 2.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="2e728-111">If that command doesn't work, make sure that .NET Core 2.0 SDK or above is installed.</span></span> <span data-ttu-id="2e728-112">Если он установлен, но команда все равно не работает, проверьте, что команда `dotnet` разрешается как минимум в версию пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="2e728-112">If it's installed, but that command still doesn't work, make sure that the `dotnet` command resolves to a version of .NET Core 2.0 SDK and above.</span></span> <span data-ttu-id="2e728-113">Воспользуйтесь командой `dotnet --version`, чтобы узнать, к которой версии `dotnet` указывает текущий путь.</span><span class="sxs-lookup"><span data-stu-id="2e728-113">Use the `dotnet --version` command to see what version of `dotnet` your current path is resolving to.</span></span> <span data-ttu-id="2e728-114">Дополнительные сведения см. в статье [Выбор версии .NET Core для использования](../versions/selection.md).</span><span class="sxs-lookup"><span data-stu-id="2e728-114">For more information, see [Select the .NET Core version to use](../versions/selection.md).</span></span>

### <a name="examples"></a><span data-ttu-id="2e728-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="2e728-115">Examples</span></span>

<span data-ttu-id="2e728-116">Ниже приведено несколько примеров возможностей, которые предоставляет автодополнение клавишей TAB:</span><span class="sxs-lookup"><span data-stu-id="2e728-116">Here are some examples of what tab completion provides:</span></span>

<span data-ttu-id="2e728-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2e728-117">Input</span></span>                                | <span data-ttu-id="2e728-118">becomes</span><span class="sxs-lookup"><span data-stu-id="2e728-118">becomes</span></span>                                                                     | <span data-ttu-id="2e728-119">because</span><span class="sxs-lookup"><span data-stu-id="2e728-119">because</span></span>
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | <span data-ttu-id="2e728-120">`add` является первой подкомандой в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="2e728-120">`add` is the first subcommand, alphabetically.</span></span>
`dotnet add p⇥`                      | `dotnet add --help`                                                          | <span data-ttu-id="2e728-121">При автодополнении клавишей TAB подстроки сопоставляются и первой по алфавиту является `--help`.</span><span class="sxs-lookup"><span data-stu-id="2e728-121">Tab completion matches substrings and `--help` comes first alphabetically.</span></span>
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | <span data-ttu-id="2e728-122">После второго нажатия клавиши TAB подставляется следующее предложение.</span><span class="sxs-lookup"><span data-stu-id="2e728-122">Pressing tab a second time brings up the next suggestion.</span></span>
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | <span data-ttu-id="2e728-123">Результаты возвращаются в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="2e728-123">Results are returned alphabetically.</span></span>
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | <span data-ttu-id="2e728-124">Автодополнение клавишей TAB зависит от файла проекта.</span><span class="sxs-lookup"><span data-stu-id="2e728-124">Tab completion is project file aware.</span></span>

## <a name="powershell"></a><span data-ttu-id="2e728-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e728-125">PowerShell</span></span>

<span data-ttu-id="2e728-126">Чтобы добавить автодополнение клавишей TAB для .NET Core CLI в **PowerShell**, создайте или измените профиль, хранящийся в переменной `$PROFILE`.</span><span class="sxs-lookup"><span data-stu-id="2e728-126">To add tab completion to **PowerShell** for the .NET Core CLI, create or edit the profile stored in the variable `$PROFILE`.</span></span> <span data-ttu-id="2e728-127">Дополнительные сведения см. в разделах [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) (Как создать свой профиль) и [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy) (Профили и политика выполнения).</span><span class="sxs-lookup"><span data-stu-id="2e728-127">For more information, see [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) and [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy).</span></span>

<span data-ttu-id="2e728-128">Добавьте в свой профиль представленный ниже код:</span><span class="sxs-lookup"><span data-stu-id="2e728-128">Add the following code to your profile:</span></span>

```powershell
# PowerShell parameter completion shim for the dotnet CLI
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a><span data-ttu-id="2e728-129">bash</span><span class="sxs-lookup"><span data-stu-id="2e728-129">bash</span></span>

<span data-ttu-id="2e728-130">Чтобы добавить автодополнение клавишей TAB для .NET Core CLI в **bash**, добавьте в свой файл `.bashrc` представленный ниже код:</span><span class="sxs-lookup"><span data-stu-id="2e728-130">To add tab completion to your **bash** shell for the .NET Core CLI, add the following code to your `.bashrc` file:</span></span>

```bash
# bash parameter completion for the dotnet CLI

_dotnet_bash_complete()
{
  local word=${COMP_WORDS[COMP_CWORD]}

  local completions
  completions="$(dotnet complete --position "${COMP_POINT}" "${COMP_LINE}" 2>/dev/null)"
  if [ $? -ne 0 ]; then
    completions=""
  fi

  COMPREPLY=( $(compgen -W "$completions" -- "$word") )
}

complete -f -F _dotnet_bash_complete dotnet
```

## <a name="zsh"></a><span data-ttu-id="2e728-131">zsh</span><span class="sxs-lookup"><span data-stu-id="2e728-131">zsh</span></span>

<span data-ttu-id="2e728-132">Чтобы добавить автодополнение клавишей TAB для .NET Core CLI в **zsh**, добавьте в свой файл `.zshrc` представленный ниже код:</span><span class="sxs-lookup"><span data-stu-id="2e728-132">To add tab completion to your **zsh** shell for the .NET Core CLI, add the following code to your `.zshrc` file:</span></span>

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete()
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```
