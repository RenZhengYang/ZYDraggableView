# ZYDraggableView
一行代码使UIView可拖动, 且放开后回弹到原位置
用法:
#import "ViewController.h"
#import "UIView+ZYDraggable.h"

@interface ViewController ()

@property (weak, nonatomic) IBOutlet UIImageView *avatarView;

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    
    // UIImageView ignored user events by default, so set
    // `userInteractionEnabled` to YES for receive touch events.
    self.avatarView.userInteractionEnabled = YES;
    
    // Make avatarView draggable
    [self.avatarView makeDraggable];
}

- (void)viewDidLayoutSubviews
{
    [super viewDidLayoutSubviews];
    
    // Update snap point when layout occured
    [self.avatarView updateSnapPoint];
}

