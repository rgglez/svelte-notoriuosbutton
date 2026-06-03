<script>
/*
   Copyright 2026 Rodolfo González González.

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
*/

  import './notorious-button.css';

  /**
   * @prop {string} label    - Button text
   * @prop {string} [class]  - Additional CSS classes
   * @prop {string} [style]  - Inline styles
   * @prop {'sweep'|'glow'|'shake'|'pulse'|'border-sweep'} [effect] - Visual effect
   * @prop {'hover'|'auto'} [trigger] - Fire effect on hover or automatically
   */
  let {
    label = 'Click me',
    class: extraClass = '',
    style: extraStyle = '',
    effect = '',
    trigger = 'hover',
    ...rest
  } = $props();
</script>

<button
  class="notorious-btn {effect ? `effect-${effect} trigger-${trigger}` : ''} {extraClass}"
  style={extraStyle}
  {...rest}
>
  {label}
</button>
