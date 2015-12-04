{dataItem}
    references dataItem variable (property) in object passed to populate template

{model.id.someId}
    references id.someId property in object 'model' in object passed to populate template

{@select key=testEnabled}
  {@any}enabled {/any}
  {@none}disabled {/none}
  {@eq value="puppies"}test-puppies{/eq}
  {@eq value="bunnies"}test-bunnies{/eq}
{/select}
    *   pass in { "testEnabled": "bunnies" }, and it renders <span class="enabled test-bunnies">

{! This gets commented out !}

{! 
    This also gets commented out 
!}

{@name_of_helper_here somekey="keyvalue"}
    content
{/name_of_helper_here}
    *  apply helper function at this object key to content inside, on somekey 


{#friends}
    {name}{@sep},{/sep}
{/friends}


{?cond}
    cond is true
{:else}
    cond is not true
{/cond}

{^cond}
    cond is false
{:else}
    cond is not false
{/cond}

{#loop}
  <label>{something}{~n}
      <option value="{value}" {@eq key=value value=courseName}selected="true"{/eq}>{label}</option>
        </label>
{:else}
    show if loop empty
{/loop}

{>partial_name /}
{>"flowViews/flowView{flowName}" /}

{@select key=\"{foo}\"}
         {@eq value=\"bar\"}foobar{/eq}
                  {@eq value=\"baz\"}foobaz{/eq}
                           {@default} - default Text{/default}
{/select}

{@select key=foo}
    {@gte value=5}foobar{/gte}
{/select}

{@if cond="{x} < {y} && {b} == {c} && '{e}'.length || '{f}'.length"}
    <div> x is less than y and b == c and either e or f exists in the output </div> 
{/if}

{@size key="xxx" }

The {@sep} helper tag will output it's body content unless this is the final iteration of the containing loop.

