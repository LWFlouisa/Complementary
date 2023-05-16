# Complementary
Complementary flavors and shades.

# Complentary Flavors
~~~ruby
# Require Ruby gems
require "naive_bayes"

# Make the labels of Naive base resemble naturalistic descriptions.
a = NaiveBayes.new(  :complement,           :noncomplement,
                     :complementary_flavor, :noncomplementary_flavor,
                     :complementary_colors, :noncomplementary_colors,
                     :poisonous,
)

a.db_filepath = "_data/complements/complements.nb"

# Train t
a.train(:complement,           "Things that go well together", "word")
a.train(:noncomplement, "Things that don't go well together.", "word")

# Complementary Flavors
a.train(:complementary_flavor,       "sweet and salty", "word")
a.train(:complementary_flavor, "peanuts and chocolate", "word")
a.train(:complementary_flavor, "caramel and chocolate", "word")
a.train(:complementary_flavor,      "cream and coffee", "word")
a.train(:complementary_flavor,  "pepper and sourkraut", "word")
a.train(:complementary_flavor, "ketchup and sourkraut", "word")

# Non Complementary Flavors
a.train(:noncomplementary_flavor,   "ketchup and chocolate", "word")
a.train(:noncomplementary_flavor, "chocolate and sourkraut", "word")
a.train(:noncomplementary_flavor,     "caramel and ketchup", "word")

a.train(:poisonous, "ammonia and chocolate", "word")

a.save
~~~

## Different Datasets
~~~ruby
# Train on different labels.
shapes  = NaiveBayes.new(:shape, :notshape)
flavors = NaiveBayes.new(:flavor, :notflavor)
shades  = NaiveBayes.new(:shade, :notshade)
devices = NaiveBayes.new(:device, :notdevice)

# Shapes
shapes.db_filepath  = "_data/shapes/shapes.nb"
flavors.db_filepath = "_data/flavors/flavors.nb"
shades.db_filepath  = "_data/shades/shades.nb"
devices.db_filepath = "_data/devices/devices.nb"

# Train on shapes
## Shade
shapes.train(:shape, "circle", "word")

## Not Shade
shapes.train(:notshape, "round", "word")

# Train on flavors
## Flavor
flavors.train(:flavor, "chocolate", "word")

## Not Flavor
flavors.train(:notflavor, "barnacle", "word")

# Train on shades
## Shade
shades.tain(:notshade, "rust", "word")

## Not Shade
shades.train(:shade, "dark", "word")

# Train on devices
## Device
devices.train(:device, "Laptop", "word")

## Not Device
devices.train(:devices, "Mineshaft", "word")

# Saving data for later
shapes.save
flavors.save
shades.save
devices.save
~~~
