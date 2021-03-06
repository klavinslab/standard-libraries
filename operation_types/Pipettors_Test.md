# Pipettors Test

Documentation here. Start with a paragraph, not a heading or title, as in most views, the title will be supplied by the view.






### Precondition <a href='#' id='precondition'>[hide]</a>
```ruby
def precondition(_op)
  true
end
```

### Protocol Code <a href='#' id='protocol'>[hide]</a>
```ruby
needs 'Standard Libs/Pipettors'
needs 'Standard Libs/LabwareNames'

class Protocol
    
  include Pipettors
  include LabwareNames

  def main

    operations.retrieve.make

    show do
      title 'Test Pipettor'
      
      note pipet(
          volume: {qty: 3.5, units: MICROLITERS},
          source: "a #{TUBE_MICROCENTRIFUGE}", 
          destination: "a new #{TUBE_MICROCENTRIFUGE}"
      )
      
      note pipet(
          volume: {qty: 35, units: MICROLITERS},
          source: "a #{TUBE_MICROCENTRIFUGE}", 
          destination: "a new #{TUBE_MICROCENTRIFUGE}"
      )
      
      note pipet(
          volume: {qty: 350, units: MICROLITERS},
          source: "the #{TUBE_15_ML_CONICAL}", 
          destination: "a new #{TUBE_MICROCENTRIFUGE}"
      )
      
      note pipet(
          volume: {qty: 37, units: MICROLITERS},
          source: "a #{TUBE_MICROCENTRIFUGE}", 
          destination: "a new #{TUBE_MICROCENTRIFUGE}",
          type: P20::NAME
      )
      
      note pipet(
          volume: {qty: 1200, units: MICROLITERS},
          source: "a #{TUBE_MICROCENTRIFUGE}", 
          destination: "a new #{TUBE_MICROCENTRIFUGE}"
      )
    end

    operations.store

    {}

  end

end

```
