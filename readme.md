### random.Int / randomInt

          ( max ) => [0, max)
          ( min, max ) => [min, max)

### random.Array / randomArray

          ( n, constructor ) => [ new constructor * n ];

### random.String / randomString

          ( number ) => [a-zA-Z0-9]*number
          ( string ) => random.Item(string)
          ( number, string ) => [char_from_string]*number
          ( template ) :
          template : [string]:\d => [string_from_chars]*n
          {[string]:\d}some_fix_string{another_template} => 
          [char_from_string]*n + some_fix_string + [char_from_another_string]*m

### random.Constructor / randomConstructor

          ( Object ) => function which generate random data :
                        val : Object            => random.Constructor( val )
                              [Function, number]=> random.Array(number,Function)
                              ['fixed', Any]    =>  Any
                              [a,b]             => random.Int(a,b)
                              function          => new function()
                              number            => random.Int(number)
                              string            => random.String(string)
### random.Item / randomItem

          ( Array | String ) => random item/char from Array/String