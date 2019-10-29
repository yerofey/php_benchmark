# php_benchmark

<b>Usage example:</b>
```php
<?php

include __DIR__ . '/benchmark.php';


// You can test a single function
benchmark([
    'func'    => 'mt_rand',
    'args'    => '1, 10',
    'repeats' => 1000,
]);

// Or a lot of functions to compare the results
benchmark([
	[
        'func'    => 'mt_rand',
        'args'    => '1, 10',
        'repeats' => 1000,
    ],
	[
        'func'    => 'rand',
        'args'    => '1, 10',
        'repeats' => 1000,
    ],
	[
        'func'    => 'intval',
        'args'    => '1, 10',
        'repeats' => 1000,
    ],
]);
```

<b>Example result:</b> <br>
Benchmark | #1: "mt_rand(1, 10)" - 0.0000002139s (1); 0.0002138615s (1,000) <br><br>
Benchmark | #1: "mt_rand(1, 10)" - 0.0000002060s (1); 0.0002059937s (1,000) <br>
Benchmark | #2: "rand(1, 10)" - 0.0000002050s (1); 0.0002050400s (1,000) <br>
Benchmark | #3: "intval(1, 10)" - 0.0000001500s (1); 0.0001499653s (1,000) - the fastest! <br>
