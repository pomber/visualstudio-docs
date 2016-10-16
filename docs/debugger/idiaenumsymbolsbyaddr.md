---
title: "IDiaEnumSymbolsByAddr"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaEnumSymbolsbyAddr interface"
ms.assetid: 37d3dcdf-e4fa-4354-b5e1-8843566b52ac
caps.latest.revision: 10
ms.author: "mikejo"
manager: "ghogen"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# IDiaEnumSymbolsByAddr
Enumerates by address the various symbols contained in the data source.  
  
## Syntax  
  
```  
IDiaEnumSymbolsByAddr : IUnknown  
```  
  
## Methods in Vtable Order  
 The following table shows the methods of `IDiaEnumSymbolsByAddr`.  
  
|Method|Description|  
|------------|-----------------|  
|[IDiaEnumSymbolsByAddr::symbolByAddr](../debugger/idiaenumsymbolsbyaddr--symbolbyaddr.md)|Positions the enumerator by performing a lookup by section and offset.|  
|[IDiaEnumSymbolsByAddr::symbolByRVA](../debugger/idiaenumsymbolsbyaddr--symbolbyrva.md)|Positions the enumerator by performing a lookup by relative virtual address (RVA).|  
|[IDiaEnumSymbolsByAddr::symbolByVA](../debugger/idiaenumsymbolsbyaddr--symbolbyva.md)|Positions the enumerator by performing a lookup by virtual address (VA).|  
|[IDiaEnumSymbolsByAddr::Next](../debugger/idiaenumsymbolsbyaddr--next.md)|Retrieves the next symbols in order by address. Updates the enumerator position by number of elements fetched.|  
|[IDiaEnumSymbolsByAddr::Prev](../debugger/idiaenumsymbolsbyaddr--prev.md)|Retrieves the previous symbols in order by address. Updates the enumerator position by number of elements fetched.|  
|[IDiaEnumSymbolsByAddr::Clone](../debugger/idiaenumsymbolsbyaddr--clone.md)|Makes a copy of an object.|  
  
## Remarks  
 This interface provides symbols grouped by address. To work with symbols grouped by type, for example `SymTagUDT` (user-defined type) or `SymTagBaseClass`, use the [IDiaEnumSymbols](../debugger/idiaenumsymbols.md) interface.  
  
## Notes for Callers  
 Obtain this interface by calling the [IDiaSession::getSymbolsByAddr](../debugger/idiasession--getsymbolsbyaddr.md) method.  
  
## Example  
 This function displays the name and address of all symbols ordered by relative virtual address.  
  
```cpp#  
void ShowSymbolsByAddress(IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumSymbolsByAddr> pEnumByAddr;  
    if ( FAILED( psession->getSymbolsByAddr( &pEnumByAddr ) ) )  
    {  
        Fatal( "getSymbolsByAddr" );  
    }  
    CComPtr<IDiaSymbol> pSym;  
    if ( FAILED( pEnumByAddr->symbolByAddr( 1, 0, &pSym ) ) )  
    {  
        Fatal( "symbolByAddr" );  
    }  
    DWORD rvaLast = 0;  
    if ( pSym->get_relativeVirtualAddress( &rvaLast ) == S_OK )  
    {  
        pSym = 0;  
        if ( FAILED( pEnumByAddr->symbolByRVA( rvaLast, &pSym ) ) )  
        {  
            Fatal( "symbolByAddr" );  
        }  
        printf( "Symbols in order\n" );  
        do  
        {   
            CDiaBSTR name;  
            if ( pSym->get_name( &name ) != S_OK )  
            {  
                printf( "\t0x%08X (%ws) <no name>\n", rvaLast );  
            }  
            else  
            {  
               printf( "\t0x%08X %ws\n", rvaLast, name );  
            }  
            pSym = 0;  
            celt = 0;  
            if ( FAILED( hr = pEnumByAddr->Next( 1, &pSym, &celt ) ) )  
            {  
                break;  
            }  
        } while ( celt == 1 );  
    }  
}  
```  
  
## Requirements  
 Header: Dia2.h  
  
 Library: diaguids.lib  
  
 DLL: msdia80.dll  
  
## See Also  
 [Interfaces (Debug Interface Access SDK)](../debugger/interfaces--debug-interface-access-sdk-.md)   
 [IDiaSession::getSymbolsByAddr](../debugger/idiasession--getsymbolsbyaddr.md)   
 [IDiaEnumSymbols](../debugger/idiaenumsymbols.md)