### money
---
https://github.com/carlospalol/money

```py
// money/tests/test_exchange.py
from __future__ import absolute_import

from decimal import Decimal
import unittest

import money.six

from money import Money, XMoney, xrates
from money.exchange import SimpleBackend
from money.exceptions import ExchangeBackendNotInstalled
from money.exceptions import ExchangeRateNotFound

class TestExchangeRateSetup(unittest.TestCase):
  def setUp(self):
    xrates.uninstall()
  
  def test_register(self):
    self.assertFalse(xrates)
    self.assertIsNone(xrates.backend_name)
    xrates.install(SimpleBackend)
    self.assertEqual(xrates.backend_name, 'SimpleBackend')
    
  def test_register_class():
  
  def test_register_instance():
  
  def test_unregister():
  
  def test_no_backend_name():
  
  def test_no_backend_base():
  
  def test_no_backend_get_rate():
  
  def test_no_backend_get_quotion():
  
  def test_multiple_xtrates(self):
  
class TestSimpleBackend(unittest.TestCase):
  def setUp(self):
    xtrates.install('money.exchange.SimpleBackend')
    xtrates.base = 'XXX'

  def test_base_property():
    self.assert
  
  def test_rate():
    self.assertIsNone(xrates.quotation('YYY', 'ZZZ'))
  
  def test_quotation(self):
    self.assertEqual(Money('10', 'AAA').to('BBB'), Money('40', 'BBB'))
    self.assertEqual(Money('10', 'BBB').to('AAA'), Money('2.5', 'AAA'))
  
  def test_unavailable_rate_returns_note():
    self.assertEqual(Money('10', 'AAA').to('BBB'), Money('40', 'BBB'))
    self.assertEqual(Money('10', 'BBB').to('AAA'), Money('2.5', 'AAA'))
    
  def test_base_not_set_warning():
    xtrates.uninstall()
    xrates.install('money.exchange.SimpleBackend')
    with self.assertRaises(Warning):
      xrates.setrate('AAA', Decimal('2'))
  
class ConversionMixin(object):
  def test_unavailable_backend_conversion_error(self):
    xtrates.uninstall()
    with self.assertRaises(ExchangeBackendNotInstalled):
      self.MoneyClass('2', 'AAA').to('BBB')
  
  def test_unavailable_rate_conversion_error(self):
    xrates.install('money.exchange.SimpleBackend')
    with self.assertRaises(ExchangeRateNotFound):
      self.MoneyClass('2', 'AAA').to('BBB')

class TestMoneyConversion(ConversionMixin, unittest.TestCase):
  MoneyClass = Money

class TestXMoneyConversion(ConversionMixin, unittest.TestCase):
  MoneyClass = XMoney
   
```

```
```

```
```

