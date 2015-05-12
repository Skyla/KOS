.. _atmosphere:

Atmosphere
==========

A Structure closely tied to :struct:`Body` A variable of type :struct:`Atmosphere` usually is obtained by the :attr:`:ATM <Body:ATM>` suffix of a :struct:`Body`. ALL The following values are read-only. You can't change the value of a body's atmosphere.

.. structure:: Atmosphere

    .. list-table::
        :header-rows: 1
        :widths: 1 1 4

        * - Suffix
          - Type
          - Description

        * - :attr:`BODY`
          - string
          - Name of the celestial body
        * - :attr:`EXISTS`
          - bool
          - True if this body has an atmosphere
        * - :attr:`OXYGEN`
          - bool
          - True if oxygen is present  
        * - :attr:`SEALEVELPRESSURE`
          - scalar (atm)
          - pressure at sea level
        * - :attr:`HEIGHT`
          - scalar (m)
          - advertised atmospheric height


.. attribute:: Atmosphere:BODY

    :type: string
    :access: Get only

    The Body that this atmosphere is around - as a STRING NAME, not a Body object.
    
.. attribute:: Atmosphere:EXISTS

    :type: bool
    :access: Get only

    True if this atmosphere is "real" and not just a dummy placeholder.
    
.. attribute:: Atmosphere:OXYGEN

    :type: bool
    :access: Get only

    True if the air has oxygen and could therefore be used by a jet engine's intake.
    
.. attribute:: Atmosphere:SEALEVELPRESSURE

    :type: scalar (atm)
    :access: Get only

    Number of Atm's at planet's sea level 1.0 Atm's = same as Kerbin.
    
.. attribute:: Atmosphere:HEIGHT

    :type: scalar (m)
    :access: Get only

    The altitude at which the atmosphere is "officially" advertised as ending. (actual ending value differs, see below).   

Atmospheric Math
----------------

The atmospheric effects of a planet's air need to be calculated using some formulas. First off, be aware that atmosphere can be measured three different ways:

Atm
    A multiple of the pressure at Kerbin sea level. An atmosphere of 0.5 is half as much air pressure as at Kerbin's sea level. This is the measure used by :SEALEVELPRESSURE
    
pressure
    A measure of the force the air pushes on a surface with. In SI units, it's Newtons per Square Meter. *This value is almost never used directly in any calculation. Instead you just calculate everything in terms of multiples of Atm's.*

density
    A measure of how much mass of air there is in a volume of space. In SI units, it's Kilograms per Cubic Meter.

