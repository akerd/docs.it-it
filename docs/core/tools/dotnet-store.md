---
title: comando dotnet store
description: Il comando 'dotnet store' archivia gli assembly specificati nell'archivio pacchetti di runtime.
author: bleroy
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: fcf1eeba0709e05cff124bc3ae7bb93f4ca57128
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-store"></a>dotnet store

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>Nome

`dotnet store`: archivia gli assembly specificati nell'[archivio pacchetti di runtime](../deploying/runtime-store.md).

## <a name="synopsis"></a>Riepilogo

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a>Descrizione

`dotnet store` archivia gli assembly specificati nell'[archivio pacchetti di runtime](../deploying/runtime-store.md). Per impostazione predefinita, gli assembly sono ottimizzati per il framework e il runtime di destinazione. Per altre informazioni, vedere l'argomento [Archivio pacchetti di runtime](../deploying/runtime-store.md).

## <a name="required-options"></a>Opzioni obbligatorie

`-f|--framework <FRAMEWORK>`

Specifica il [framework di destinazione](../../standard/frameworks.md).

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

Il *file manifesto dell'archivio pacchetti* è un file XML che contiene l'elenco di pacchetti da archiviare. Il formato del file manifesto è compatibile con il formato *csproj*. È quindi possibile usare un file di progetto *csproj* che fa riferimento ai pacchetti desiderati con l'opzione `-m|--manifest` per archiviare gli assembly nell'archivio pacchetti di runtime. Per specificare più file manifesto, ripetere l'opzione e il percorso per ogni file: `--manifest packages1.csproj --manifest packages2.csproj`.

`-r|--runtime <RUNTIME_IDENTIFIER>`

L'identificatore di runtime di destinazione.

## <a name="optional-options"></a>Opzioni facoltative

`--framework-version <FRAMEWORK_VERSION>`

Specifica la versione di .NET Core SDK. Questa opzione consente di selezionare una versione di framework specifica, oltre al framework specificato dall'opzione `-f|--framework`.

`-h|--help`

Visualizza le informazioni sulla guida.

`-o|--output <OUTPUT_DIRECTORY>`

Specifica il percorso dell'archivio pacchetti di runtime. Se non viene specificato, per impostazione predefinita viene usata la sottodirectory *store* della directory di installazione di .NET Core del profilo utente.

`--skip-optimization`

Ignora la fase di ottimizzazione.

`--skip-symbols`

Ignora la generazione di simboli. Attualmente è possibile generare simboli solo in Windows e Linux.

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

Directory di lavoro usata dal comando. Se non viene specificata, viene usata la sottodirectory *obj* della directory corrente.

## <a name="examples"></a>Esempi

Archiviare i pacchetti specificati nel file di progetto *packages.csproj* per .NET Core 2.0.0:

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

Archiviare i pacchetti specificati nel file di progetto *packages.csproj* senza ottimizzazione:

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a>Vedere anche

[Archivio pacchetti di runtime](../deploying/runtime-store.md)   
