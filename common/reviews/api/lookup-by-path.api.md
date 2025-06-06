## API Report File for "@rushstack/lookup-by-path"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

// @beta
export function getFirstDifferenceInCommonNodes<TItem extends {}>(options: IGetFirstDifferenceInCommonNodesOptions<TItem>): string | undefined;

// @beta
export interface IGetFirstDifferenceInCommonNodesOptions<TItem extends {}> {
    delimiter?: string;
    equals?: (a: TItem, b: TItem) => boolean;
    first: IReadonlyPathTrieNode<TItem>;
    prefix?: string;
    second: IReadonlyPathTrieNode<TItem>;
}

// @beta
export interface IPrefixMatch<TItem extends {}> {
    index: number;
    lastMatch?: IPrefixMatch<TItem>;
    value: TItem;
}

// @beta
export interface IReadonlyLookupByPath<TItem extends {}> extends Iterable<[string, TItem]> {
    [Symbol.iterator](query?: string, delimiter?: string): IterableIterator<[string, TItem]>;
    entries(query?: string, delimiter?: string): IterableIterator<[string, TItem]>;
    findChildPath(childPath: string, delimiter?: string): TItem | undefined;
    findChildPathFromSegments(childPathSegments: Iterable<string>): TItem | undefined;
    findLongestPrefixMatch(query: string, delimiter?: string): IPrefixMatch<TItem> | undefined;
    get(query: string, delimiter?: string): TItem | undefined;
    groupByChild<TInfo>(infoByPath: Map<string, TInfo>, delimiter?: string): Map<TItem, Map<string, TInfo>>;
    has(query: string, delimiter?: string): boolean;
    get size(): number;
    // (undocumented)
    get tree(): IReadonlyPathTrieNode<TItem>;
}

// @beta
export interface IReadonlyPathTrieNode<TItem extends {}> {
    readonly children: ReadonlyMap<string, IReadonlyPathTrieNode<TItem>> | undefined;
    readonly value: TItem | undefined;
}

// @beta
export class LookupByPath<TItem extends {}> implements IReadonlyLookupByPath<TItem> {
    [Symbol.iterator](query?: string, delimiter?: string): IterableIterator<[string, TItem]>;
    constructor(entries?: Iterable<[string, TItem]>, delimiter?: string);
    clear(): this;
    deleteItem(query: string, delimeter?: string): boolean;
    deleteSubtree(query: string, delimeter?: string): boolean;
    readonly delimiter: string;
    entries(query?: string, delimiter?: string): IterableIterator<[string, TItem]>;
    findChildPath(childPath: string, delimiter?: string): TItem | undefined;
    findChildPathFromSegments(childPathSegments: Iterable<string>): TItem | undefined;
    findLongestPrefixMatch(query: string, delimiter?: string): IPrefixMatch<TItem> | undefined;
    get(key: string, delimiter?: string): TItem | undefined;
    groupByChild<TInfo>(infoByPath: Map<string, TInfo>, delimiter?: string): Map<TItem, Map<string, TInfo>>;
    has(key: string, delimiter?: string): boolean;
    static iteratePathSegments(serializedPath: string, delimiter?: string): Iterable<string>;
    setItem(serializedPath: string, value: TItem, delimiter?: string): this;
    setItemFromSegments(pathSegments: Iterable<string>, value: TItem): this;
    get size(): number;
    // (undocumented)
    get tree(): IReadonlyPathTrieNode<TItem>;
}

```
