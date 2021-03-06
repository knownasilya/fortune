# To-do list

*This file is marked for deletion after 1.0.*

- Website layout redux (?)
- Consider using ES7 features (?)
- IndexedDB adapter.
- Test create/update payloads that link to each other within the payload.
- Improve inflection to also use dasherize.
- Test the default serializer.
- PostgreSQL adapter.
- 100% test coverage.


### Done

- Consider writing default adapter with Loki.js (decided: go straight for IndexedDB).
- There are some validations that could be added to record field definitions since Fortune is already concerned with them, such as `isUnique` and `isNullable` (decided: this should be done on a per adapter basis).
- Core build.
- Support record types with arbitrary fields (decided: no)
- Serializer errors should default to BadRequestError.
- Remove implementation from Serializer class, move to DefaultSerializer.
- Encode URI in serializers, important for unicode types/IDs/fields, etc.
- Options discovery (show `Allow` header).
- Use `some` or `every` instead of `find` or `includes` where possible.
- Rename reserved_keys -> keys, schemas -> recordTypes, schema -> fields, schema[field] => fieldDefinition.
- POST record with ID in route (decided: nope).
- Mix and match serializer testing (disabled for now).
- Make denormalized fields not enumerable in the adapter.
- Obfuscate Micro API URIs, to make it clear that hypermedia should be used.
- Use `t.comment()` for testing.
- Micro API Serializer: tests.
- Remove the ability to create related resources on POST for JSON API.
- Do more memoization of object-key lookups: `const value = object[key]` (postponed, it's effectively O(1)).
- Lower cyclomatic complexity (postponed, seems to be a largely useless metric).
- Buffer comparison in NeDB adapter.
- Use `for...of` loop everywhere instead of `forEach`.
- Unset 2nd degree related records for push/pull updates.
- Make `serializerInput` and `serializerOutput` optional.
- Refactor requestListener -> http.
- Hide denormalized inverse fields somehow.
- Automatically denormalize inverse fields.
- Stub apply update method in Adapter.
- Replace `indexOf` with `includes`, add to array proxy.
- Integration test for standard serializer.
- Update workflow: consistency checks, change event.
- Make sure that a record cannot link to itself on update (should use `enforce` function for this).
- Enforce referential integrity.
- Attach IDs to related records on related creation for JSON API (handled in schema design and middleware).
- Add `update` test for adapter.
- Ensure created records have empty arrays for array fields.
- Consider removing `include` and `optionsPerType` and moving them to the serializer (Answer: No, serializers have to define display of included records).
- Add `setAdapter` and `addSerializer` methods.
- Inverse fields can only be bi-directional.
- Refactor `do_create` now that `relatedField` is removed.
- Make `inverse` field required for links, run static analysis on linking ontology when `initialize` is called.
- Remove `fetchRelated` and `relatedField` from the dispatcher. This feature belongs in serializers.
- Make serializer process methods asynchronous.
- NeDB Adapter.
- Delete workflow.
- HTTP miscellaneous features.
- Replace `idCache` with `Set` type.
- Move `transaction` instance to `context`, make `change` event data from transaction (won't do, not a good idea).
- Dispatcher should do all adapter calls to sync inverse relationships.
- Consider if Fortune can be isomorphic (run on server and client). Answer: it already should.
- Internal refactor of actions into flows.
- Dependency injection for adapter/serializer.
- Known bug: Array.prototype.find doesn't work correctly with babel-runtime. Resolved by using proxy method for find.
- Consider using [URI Template](http://tools.ietf.org/html/rfc6570).
- Changed signature of transform function. Now record is accepted as second parameter and `this` is no longer bound.
- Add optional `processRequest` and `processResponse` in serializer.
- Remove `bufferEncoding` option. Superceded by `schema` options object.
- How to remove `_records` and `_include` from response object? Done in `_processResponse` now.
- Remove 6to5 from distribution.
- Pagination (limit and offset options in the adapter).
- Add serializer hooks to allow the entire request/response payload to be transformed (useful for "meta" object). Implemented as `Serializer.processRequest`.
- Reorganize file/folder structure.
- Server initialization method? This is now handled separately from core module.
- Should serializer process query strings? Leaning towards no since that is HTTP, but maybe? Actually I think it should though. Now it is implemented as `Serializer.processRequest`.
- Request options should be specific to a type.
- Make dispatcher call stubs to adapter for ACID transactions.
- Option to disable casting and mangling of buffers? Now this option exists on `Schema.Enforcer`.
- Removed `inflect` and `prefix` options, these should be handled per serializer.
- Make serializer methods return context, this makes life easier.
- Create linked record if there was a related field.
- Include uniqueness problem if original request does not supply IDs.
- Primary key configuration.
- Minimize or eliminate `indexOf`, `map`, `reduce` calls.
- ID requirement? Primary key? Problem with checking object sameness for includes by ID. Resolved with ID lookup hash table.
- Schema enforcement during I/O.
- Ordered serializers by priority.
- Typed errors.
- Remove the `_relatedType` and `_relatedIds`.
- Dispatcher abstraction from HTTP, consolidate `request` and `response` in the `context` object.
- Remove `require` calls in Serializer and Adapter. Resolved by removing strings.
